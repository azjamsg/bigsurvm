# How to Create macOS Big Sur ISO Image File

## Steps to Create macOS Big Sur ISO File

   1. Download macOS Big Sur From Apple

   2. Create & Mount an empty Disk Image using hdiutil<br>
   ⋅⋅⋅	2.1. Once macOS is downloaded then Open Terminal and type the following command to create an empty disk image. Type your password when prompted.
      (sudo hdiutil create -o /tmp/BigSur -size 16384m -volname BigSur -layout SPUD -fs HFS+J)
   ⋅⋅⋅2.2. Next, Mount the disk image to /Volumes/BigSur.
      (sudo hdiutil attach /tmp/BigSur.dmg -noverify -mountpoint /Volumes/BigSur)   
      
   3. Use the Createinstallmedia command to make the disk image bootable with macOS
   ⋅⋅⋅3.1. Now will use the Createinstallmedia command to make the disk image bootable with macOS Big Sur.
      (sudo /Applications/Install\ macOS\ Big\ Sur.app/Contents/Resources/createinstallmedia --volume /Volumes/BigSur --nointeraction)

   4. Unmount the Disk Image
   ⋅⋅⋅4.1. Unmount the Disk Image which is formatted from BigSur to Install macOS Big Sur and bootable with macOS Big Sur ISO image.
      (hdiutil eject -force /Volumes/Install\ macOS\ Big\ Sur)
   
   5. Covert the Disk Image to ISO image
   ⋅⋅⋅5.1. Covert and rename the Disk Image to ISO
      (hdiutil convert /tmp/BigSur.dmg -format UDTO -o ~/Desktop/BigSur
       mv -v ~/Desktop/BigSur.cdr ~/Desktop/BigSur.iso
       sudo rm -fv /tmp/BigSur.dmg)
