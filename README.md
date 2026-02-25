# ASR-GUI: Offline Speech To Text Web Application

**Name:** Tan Liang Meng    
**Project Title:** Full Stack Development & Deployment of ASR GUI  
**Supervisor:** Prof Chng Eng Siong  
**Start Date:** 11 Aug 2025
**End Date:** 23 Mar 2026  

## Overview
ASR-GUI is an offline web application designed to operationalize high-accuracy speech recognition models. The system provides a full-lifecycle solution for managing recordings, from secure upload and automated transcription to final export, all within a centralized, containerized environment. 

Initially, the project existed as a basic proof-of-concept that supported simple end-to-end workflows but suffered from critical limitations: it restricted users to sequential, single-job processing, only supported lossless WAV audio formats, and lacked adequate safeguards for data persistence. 

Inheriting this legacy codebase, my core responsibility is to re-engineer the application to improve its operational efficiency and bridge the gap between a functional proof-of-concept and a more robust, user-friendly tool

## Video Updates
**Playlist:** https://www.youtube.com/playlist?list=PLRbZvpXyAtmDoMQaCJ0HLC_bzqJQYA1tn 

## Milestones

### 1. High-Throughput Batch Processing
*  **Parallel Architecture**: Re-engineered the sequential workflow into a parallel processing model using asynchronous HTTP requests to enable simultaneous transcription and deletion of multiple recordings.
*  **Dual-Mode Configuration**: Introduced a flexible interface allowing users to toggle between a "Global Mode" for uniform batch settings and an "Individual Mode" for distinct file configurations in a single workflow.

### 2. Real-Time System Feedback
*  **Byte-Accurate Tracking**: Replaced hardcoded feedback timers with an Axios-based monitoring system that tracks real-time data transmission.
*  **Visual Progress Indicators**: Implemented live percentage completion bars based on actual bytes loaded, providing clear visibility for high-volume upload operations.

### 3. Media Compatibility Expansion
*  **Format Versatility**: Expanded system ingestion beyond legacy WAV files to support MP3, MP4, M4A, and WebM formats.

### 4. Data Integrity & Reliability
*  **Orphan Prevention**: Implemented a deletion lock on active transcription jobs to prevent the removal of source files currently undergoing inference.
*  **Sequential Deletion Protocol**: Established a "Database-First" deletion order to ensure metadata is removed from MongoDB before cleaning up physical files in Docker volumes.

### 5. Hotword UI/UX Enhancements
*  **Bulk Alias Management**: Upgraded the Hotword interface to support the addition of entire lists of aliases separated by commas, eliminating repetitive manual entries.
* **Modernized Workflow**: Introduced a centralized hamburger action menu for cleaner navigation, a safer deletion confirmation process, and auto-persistence to ensure every change is saved instantly.
