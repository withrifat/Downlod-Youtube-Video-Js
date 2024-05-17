# Downlod Youtube Video Js
 this tool is used in consol for downlod youtube playlist
Learn How to Copy YouTube playlist video URLs using code in 2023

Step 1: To begin, launch your preferred web browser and access the YouTube playlist page that contains the desired video titles and URLs for extraction. As an illustration, let’s consider a popular YouTube music playlist as an example. To reach the playlist page where all the videos are situated, simply click on the playlist name as demonstrated in the video tutorial.
Step 2: To initiate the data extraction process, you’ll need to access the browser console. This is typically achieved by accessing the developer tools of your browser and locating the console tab. Once you’ve located the console, click on it to open it. Once the console is open, you can proceed by pasting the provided JavaScript code snippets to continue with the extraction.
Step 3: To activate the automated scrolling function, open the browser console and paste the first code snippet labeled as “Code snippet 1”. This snippet will initiate the automated scrolling process, allowing us to gather the necessary data from the YouTube playlist. Here is the code snippet for your reference:
    //COPY & PASTE CODE 1:

    let goToBottom = setInterval(() => window.scrollBy(0, 400), 1000);
Once you have pasted the code snippet into the console and pressed the ENTER key, the page will commence automatic scrolling. Kindly remain patient until the scrolling reaches the bottom of the page. This scrolling procedure is crucial for collecting all the video titles and URLs from the YouTube playlist.

Step 4: Once the scrolling action concludes, you can continue by pasting the second code snippet labeled as “Code snippet 2”. This specific code snippet is designed to extract the video titles and URLs from the YouTube playlist and showcase them in the console. Here is the code snippet for your convenience:

    //COPY & PASTE CODE 2:

    clearInterval(goToBottom);
    let arrayVideos = [];
    console.log('\n'.repeat(50));
    const links = document.querySelectorAll('a');
    for (const link of links) {
    if (link.id === "video-title") {
        link.href = link.href.split('&list=')[0];
        arrayVideos.push(link.title + ';' + link.href);
        console.log(link.title + '\t' + link.href);
    }
    }
Upon pasting the second code snippet, the console will exhibit the video titles and URLs in the desired format. At this point, you have the option to copy this data and paste it into a spreadsheet for additional analysis or any other purpose you deem necessary.

Step 5: Optional Step – To proceed with exporting the data as a CSV file, you can follow an optional step. This step enables you to download the data in CSV format, utilizing a semicolon (;) as the separator.

To proceed, simply copy the provided code snippet labeled as “Code snippet 3”. Here’s the code snippet:

    //COPY & PASTE CODE 3:

    let data = arrayVideos.join('\n');
    let blob = new Blob([data], {type: 'text/csv'});
    let elem = window.document.createElement('a');
    elem.href = window.URL.createObjectURL(blob);
    elem.download = 'my_data.csv';
    document.body.appendChild(elem);
    elem.click();
    document.body.removeChild(elem);
By pasting the code snippet, a CSV file named “my_data.csv” will be automatically downloaded.

This file will contain the video titles and URLs in a format suitable for spreadsheet applications.