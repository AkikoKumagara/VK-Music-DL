<h1 align="center">VK Music DL</h1>
<p align="center">A method to download and combine segmented audio files painlessly.</p>

<p align="center">Work around their abstraction. We own them.</p>

<h2 align="center">The process and why it's needed</h2>

Services such as VK split audio files into a bunch of .ts files containing segments of the original file, then control them via a playlist file with the extension .m3u8.

Using curl you can batch download the .ts files because they are numbered sequentually.

Example of how to download:

```
curl -o "index.m3u8" https://psv4.vkuseraudio.net/s/v1/a2/SFIHgtmyBk04qWBrFhk8wG165o9mBCnFVT7c4rNw_d_3ojM6qzUi4-bMz53RvpLdMsu0tbrhx9kgEFFb-5vZFeP60Kgg1UmgCZ1eAQZo3kX-e7LdHZ74wi1rJ1n0sXffrIZMhkcAK9gZLynvLcEmRwuYDWe8d4b1iA/index.m3u8
```
```
curl -o "seg-#1-a1.ts" https://psv4.vkuseraudio.net/s/v1/a2/SFIHgtmyBk04qWBrFhk8wG165o9mBCnFVT7c4rNw_d_3ojM6qzUi4-bMz53RvpLdMsu0tbrhx9kgEFFb-5vZFeP60Kgg1UmgCZ1eAQZo3kX-e7LdHZ74wi1rJ1n0sXffrIZMhkcAK9gZLynvLcEmRwuYDWe8d4b1iA/seg-[1-22]-a1.ts```
```
The URL for the `index.m3u8` file and the segmented `.ts` files can be found by simply monitoring network through your web browser's inspector when you play the audio.
Fill in the number of segments inside the braces with a range; in my example it's [1-22] as there are 22 segment files here.

After this, we use VLC Media Player's Convert/Save functions to finish the job and combine our segmented `.ts` files into a single file by opening the `.m3u8` in the Save/Convert window.

I recommend using WAV format + Keep Original Audio Track setting for the highest quality available.

Follow the settings in the screenshots below, or adjust them to your liking.

![image](https://user-images.githubusercontent.com/15231336/229363980-85c37d9d-1db2-42db-9b78-387b40546fbb.png)

![image](https://user-images.githubusercontent.com/15231336/229363955-1dcc9708-ae10-468e-bbb2-2c88155c8f69.png)

![image](https://user-images.githubusercontent.com/15231336/229363963-f915739b-ab31-4817-ad14-0cadddb3a3a7.png)


-----

Note: I own the copyright to the files used in my example. These files are being downloaded with my permission. This method is not meant to be used as a means of piracy, but rather preservation of music/audio one may want to rightfully download and save.
