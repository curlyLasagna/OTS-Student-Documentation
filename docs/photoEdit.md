# Virtual Tour Photos
Editing photos is fairly simple, yet cumbersome. Make sure you have Adobe Photoshop installed.  
Also ensure that you have the original copies of the pictures stored in your One Drive. You have 1TB of free cloud storage, abuse it.

## Directories structure
Dump the unedited pictures in a new folder called "Originals"  
Create a new folder called "Finished", which stores the edited photos

## Editing photos
1. Right click the image you've taken and open with "Adobe Photoshop".
2. Click the Crop Tool ![crop tool](https://helpx.adobe.com/content/dam/help/icons/SP_Crop_Lg_N_D.png) if it's not set already.
3. Drag the square around to crop out the part that you want to keep.
4. You can also rotate the picture around so that it looks straight.

### Perspective Warp

This tool is useful if you want to modify a picture that was taken at at an angle so that it appears straight.


### Exporting the edited photo

1. Photos must be saved with a resolution of 640x480. (Seriously, what year is it again?)
2. Set the height or width, whichever is highest to 640 and Photoshop will automagically set the other value so that the photo's respective aspect ratio is kept.
3. Save it in the "Finished" folder

#### Setting the title

The title of the COLLECTIONS image is particular.

I created this Python script to generate all possible COLLECTIONS title.

```python
"""Returns the title of a COLLECTIONS image for the virtual tour

Any images with the prefix of COLLECTIONS must follow the structure to be outputted to be valid

Args:
    collectionCode (str): The room number or collection code of the appropriate image

Returns:
    list (str): List of strings with the collection code and the suffixes 

"""
def returnTitle(collectionCode: str) -> list[str]:
    collectionSuffix = [
        "View From Front",
        "View From Back",
        "Instructor Workstation",
        "Instructor Workstation Components",
    ]

    return [f"COLLECTIONS_{collectionCode}_{s}" for s in collectionSuffix]


while True:
    collectionCode = (
        input("Enter in 'q' to quit\nEnter the collection code of the room: ")
        .replace(" ", "")
        .upper()
    )

    if collectionCode == "Q":
        run = False
        break
    else:
        print("\nCOLLECTIONS image titles:\n")
        for title in returnTitle(collectionCode):
            print(f"{title}\n")

```

## Uploading edited photos to the production site
> Whatever you do to the Virtual Tour directory will reflect on the actual website, so traverse and modify files with caution

### When there's equipment that has been replaced or removed

1. Create a list of equipment that's been removed from the room.
2. Delete the pictures of the list of equipment that's been removed.
3. Copy over the photos in the "Finished" directory.
   - Click yes to overwrite files with the same title

