#!/bin/bash

echo "======================================"
echo "         FILE ORGANIZER PROGRAM"
echo "======================================"
echo "This program organizes the files in your current directory."
echo "You can choose to organize images, documents, videos,"
echo "or all types of files at once."
echo "======================================"
echo
echo "1. Organize Images"
echo "2. Organize Documents"
echo "3. Organize Videos"
echo "4. Organize All Files"
echo "5. Exit"
echo

read -p "Enter your choice: " choice

organize_images() {
    mkdir -p Images
    mv *.jpg *.png *.jpeg Images/ 2>/dev/null
}

organize_docs() {
    mkdir -p Documents
    mv *.txt *.pdf *.docx Documents/ 2>/dev/null
}

organize_videos() {
    mkdir -p Videos
    mv *.mp4 *.mkv *.avi Videos/ 2>/dev/null
}

organize_all() {
    organize_images
    organize_docs
    organize_videos
}

case $choice in
    1) organize_images ;;
    2) organize_docs ;;
    3) organize_videos ;;
    4) organize_all ;;
    5) exit ;;
    *) echo "Invalid choice" ;;
esac

echo "Task Completed."
