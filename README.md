// Import the necessary libraries
import { contentScript } from 'chrome-extension';

// Define the content script
const contentScript = contentScript({
  // The script will run on all pages
  matches: ['*'],

  // The script will run when the page is loaded
  onLoad: () => {
    // Get the element that contains the game
    const gameElement = document.querySelector('#game-container');

    // Make the element transparent
    gameElement.style.backgroundColor = 'rgba(0, 0, 0, 0)';
  },
});

// Register the content script
chrome.runtime.onInstalled.addListener(() => {
  chrome.scripting.registerContentScript(contentScript);
});
