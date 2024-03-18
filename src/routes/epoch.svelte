<script>
    let selectedEpoch = options[0]; // This will hold the currently selected epoch
    let selectedTestAcc; // This will be updated to show the test accuracy for the selected epoch
    let selectedTestLoss; // This will be updated to show the test loss for the selected epoch
  
    const options = [1, 3, 5, 10, 25, 50, 75, 100];

    // Data object holding the Test Accuracy and Test Loss values for each epoch
    const results = {
      1: {testAcc: 0.9087, testLoss: 0.3115},
      3: {testAcc: 0.9168, testLoss: 0.3013},
      5: {testAcc: 0.9222, testLoss: 0.2879},
      10: {testAcc: 0.9238, testLoss: 0.2814},
      25: {testAcc: 0.9258, testLoss: 0.2814},
      50: {testAcc: 0.9222, testLoss: 0.2879},
      75: {testAcc: 0.9258, testLoss: 0.2814},
      100: {testAcc: 0.9258, testLoss: 0.2814}
    };
  
    // Whenever selectedEpoch changes, this reactive statement will update the accuracy and loss
    $: if (selectedEpoch) {
      selectedTestAcc = results[selectedEpoch]?.testAcc ?? 'N/A';
      selectedTestLoss = results[selectedEpoch]?.testLoss ?? 'N/A';
    }
  </script>
  
  <!-- Dropdown for selecting an epoch -->
  <select bind:value={selectedEpoch}>
    <option value="" disabled>Select Epoch</option>
    {#each Object.keys(results) as epoch}
      <option value={epoch}>{epoch}</option>
    {/each}
  </select>
  
  <!-- Display the selected values -->
  {#if selectedEpoch}
    <p>Selected Epoch: {selectedEpoch}</p>
    <p>Test Accuracy: {selectedTestAcc}</p>
    <p>Test Loss: {selectedTestLoss}</p>
  {/if}

  <svelte:element this={selectedEpoch}>Selected Epoch: {selectedEpoch}</svelte:element>