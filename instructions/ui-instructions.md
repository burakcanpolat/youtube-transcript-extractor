# Instructions for UI and Structural Changes

## 1. Implement Separate Progress Bars with Timers for Each Phase

### Scraping Transcripts
- Create a progress bar labeled "Scraping Transcripts"
- Update the progress bar based on the number of videos scraped out of the total selected
- Display an elapsed time counter next to or below the progress bar

### Processing via OpenAI API
- Create a progress bar labeled "Processing Transcripts"
- Update the progress bar based on the number of videos processed out of the total
- Display an elapsed time counter
- If possible, show details such as the title of the video currently being processed

### Merging Files
- Create a progress bar labeled "Merging Transcripts"
- Update it when the merging process starts and completes
- Display an elapsed time counter

## 2. Modify Buttons for Process Initiation and Download

### "Process Transcripts" Button
- Rename the existing "Download Selected Transcripts" button to "Process Transcripts"
- When clicked, initiate the scraping, processing, and merging phases
- Do not trigger an automatic download upon completion

### "Download Transcripts" Button
- Add a new button labeled "Download Transcripts"
- Keep this button disabled or hidden until all processing is complete
- Enable or reveal it once the merged file is ready for download

## 3. Display Time Taken for Each Stage
- For each phase (Scraping, Processing, Merging), display the total time taken upon completion
- Optionally, display the estimated remaining time during each phase based on current progress

## 4. Enhance UI Layout
- Organize the progress bars and timers vertically or in a tabbed interface to maintain a clean layout
- Ensure all elements are responsive and adapt to different screen sizes
- Use clear labels and tooltips to improve user understanding

## 5. Asynchronous Processing and UI Updates
- Refactor the code to handle each phase asynchronously to keep the UI responsive
- Use asynchronous functions or promises to update progress bars and timers in real-time
- Ensure that the main thread is not blocked during API calls or file operations

## 6. Provide Detailed Processing Information

### During the OpenAI API processing phase, display:
- The name or index of the current video being processed
- Individual progress if processing time per video is significant
- Optionally, include a collapsible section to show or hide detailed logs

## 7. Implement Performance Tracking
- Log the start and end times of each phase to calculate durations
- Store these durations and display them in a summary section after processing completes
- Use this data to identify bottlenecks and optimize performance in future iterations

## 8. Testing and Validation
- Test the new UI components to ensure progress bars and timers update correctly
- Verify that the "Process Transcripts" button initiates all phases without downloading
- Ensure the "Download Transcripts" button only becomes active after processing is complete
- Check that time displays are accurate and reset appropriately between sessions

## 9. User Experience Enhancements
- Add confirmation messages or notifications when each phase completes
- Provide error handling and display user-friendly messages if any phase fails
- Allow users to cancel ongoing processes if necessary

## 10. Code Comments and Documentation
- Comment the new code sections for clarity
- Update any existing documentation to reflect the UI and structural changes

## Summary

- **Add separate progress bars and timers** for Scraping, Processing, and Merging phases to provide detailed progress tracking
- **Split the existing button** into "Process Transcripts" to start processing and "Download Transcripts" to download the file when ready
- **Display detailed information and time metrics** to help users understand the software's performance
- **Refactor the code for asynchronous execution** to keep the UI responsive and update progress in real-time
- **Enhance the overall user experience** with clear labels, error handling, and optional detailed logs