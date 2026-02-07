** This project demonstrates the implementation and execution of Montreal Forced Aligner (MFA) using Docker containers.
MFA is used for speech-to-text alignment, which aligns audio recordings with their corresponding transcripts at the phoneme level.

Docker Installation
Windows Installation Steps:
Download Docker Desktop from docker.com/products/docker-desktop

Run the installer with default settings

Enable WSL2 (Windows Subsystem for Linux) when prompted

Restart your computer after installation

Verify Installation: powershell  -->>  docker --version

Docker Commands for the execution of MFA : 
1. docker image pull mmcauliffe/montreal-forced-aligner:latest
2. docker run -it --rm `
>>   -v "$env:USERPROFILE\Desktop\mfa_data:/data" `
>>   mmcauliffe/montreal-forced-aligner:latest `
>>   mfa align /data /data/english_mfa.dict /data/english_mfa.zip /data/output

Mfa : https://montreal-forced-aligner.readthedocs.io/en/latest/installation.html
Acoustic Model : https://mfa-models.readthedocs.io/en/latest/acoustic/English/index.html
Dicstionaries : https://mfa-models.readthedocs.io/en/latest/dictionary/English/index.html 

<img width="1609" height="762" alt="Screenshot 2026-02-07 222455" src="https://github.com/user-attachments/assets/c324790a-062c-408c-b8ba-d5d2d74039cd" />

Output summary  : 
 INFO     Setting up corpus information...
 INFO     Loading corpus from source files...
   6% ━━━━╸━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 6/100  [ 0:00:03 < 0:00:18 , 5 it/s ]
 INFO     Found 1 speaker across 6 files, average number of utterances per speaker: 6.0
 INFO     Initializing multiprocessing jobs...
 WARNING  Number of jobs was specified as 3, but due to only having 1 speakers, MFA will only use 1 jobs. Use the
          --single_speaker flag if you would like to split utterances across jobs regardless of their speaker.
 INFO     Normalizing text...
 100% ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 6/6  [ 0:00:01 < 0:00:00 , ? it/s ]
 INFO     Generating MFCCs...
 100% ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 6/6  [ 0:01:08 < 0:00:00 , 2 it/s ]
 INFO     Calculating CMVN...
 INFO     Generating final features...
 100% ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 6/6  [ 0:00:01 < 0:00:00 , ? it/s ]
 INFO     Creating corpus split...
 100% ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 6/6  [ 0:00:01 < 0:00:00 , ? it/s ]
 INFO     Compiling training graphs...
 INFO     Performing first-pass alignment...
 INFO     Generating alignments...
 100% ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 6/6  [ 0:00:04 < 0:00:00 , ? it/s ]
 INFO     Collecting phone and word alignments from alignment lattices...
 100% ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 6/6  [ 0:00:02 < 0:00:00 , ? it/s ]
 INFO     Analyzing alignment quality...
 100% ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 6/6  [ 0:00:07 < 0:00:00 , ? it/s ]
 INFO     Exporting alignment TextGrids to /data/output...
 100% ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 6/6  [ 0:00:00 < 0:00:00 , 16 it/s ]
 INFO     Finished exporting TextGrids to /data/output!
 INFO     Done! Everything took 225.113 seconds   
