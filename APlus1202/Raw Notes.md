# Operating Systems Overview: 1.1
## Why do you need an OS
- Control interaction between components
	- Memory, hard drives, keyboard, CPU
- A common platform for applications
	- You're going to do some work, right?
- Humans need a way to interact with the machine
	- The user interface
	- Hardware can't do everything

## Standard OS features
- File management
	- Add, delete, rename
- Application support
	- Memory management, swap file management
- Input and Output support
	- Printers, keyboards, storage drivers, USB drives
- Operating system configuration and management tools

## Microsoft Windows
- Major market presence 
- Many different versions
- Advantages
	- Large industry support
	- Broad selection of OS option
	- Wide variety of software support
- Disadvantages
	- Large install base provides a big target for security exploitation
	- Large hardware support can create challenging integration exercises.

## Linux
- Free Unix-compatible software system
	- Unix like, but not unix
- Many different distributions
	- Ubuintu, debian, red hat/fedora
- Advantages
	- Free
	- Works on wide variety of hardware
	- Passionate and active user community
- Disadvantages
	- Limited driver support, especially with laptops
	- Limited support options

## Apple macOS
- macOS
	- Desktop OS running on Apple hardware
- Advantages
	- Easy to use
	- extremely compatible
	- Relatively fewer security concerns
- Disadvantages
	- Requires Apple hardware
	- Less industry support than the PC platform
	- Higher initial hardware cost

## Chrome OS
- Google's operating system
	- Based on the Linux kernel
- Centers around chrome web browser
	- Most apps are web based
- Many different manufacturers
	- Relatively less expensive
- Relies on the cloud
	- Connect to the Internet

## Apple iPadOS
- Operating system for Apple's IPad Tablets
- Tablet Features
	- Desktop browser (Safari)
	- Second monitor (Sidecar)
	- Keyboard support
	- Multitasking

## Apple iOS
- Apple iOS
	- Apple iPhones
	- Based on Unix
	- Closed source, no access to source code
	- Exclusive to apple products
- iOS Apps
	- Apps are developed with Apple's SDK on macOS
	- Apps must be approved by Apple before release
	- Apps are available to users in the Apple App Store

## Google Android
- Google Android
	- Open Handset Alliance
	- Open source, OS, based on Linux
	- Supported on many different manufacturer's devices
- Android Apps
	- Apps are developed on Windows, macOS, and Linux with the Android SDK
	- Apps available from Google Play
	- Apps also available from third-party sites

## Vendor specific limitations
- End of life
	- Different companies set their own EOL policies
- Updating
	- iOS, Android, and Windows check and prompt for updates
	- Chrome OS will update automatically
- Compatibility between operating systems
	- Some movies and music can be shared 
- Almost no direct application compatibility
	- Fortunately, many apps have been built to run on different OSes
	- Some data files can be moved across systems
	- Web based apps have potential

# File Systems: 1.1
## File Systems
- Before data can be written to the partition, it must be formatted
	- Build the foundation
- Operating systems expect data to be written in a particular format
	- FAT32 and NFTS are popular
- Many operating systems can read (and sometimes write) multiple file system types
	- FAT, FAT32, NTFS, exFAT, etc
## NTFS
- NTFS - NT File System
	- Extensive improvements over FAT32
	- Quotas, file compression, encryption, symbolic links, large file support, security, recoverability
- Not very compatible across operating systems
	- Many OSes will read NTFS but not write
	- Some have limited write functionality to an NTFS file system
## Resilient File System (ReFS)
- The Future of Windows file systems
	- An update to NTFS
	- Server 2012 and later, limited support in Windows 8.1 and later
- Huge storage requirements
	- Support for very large drives and storage arrays
- Constant data availability
	- Self repairing, ongoing integrity checks, no more chkdsk!
	- The file system also provides RAID-like redundancy
- A measured integration
	- Updates and improvements are ongoing
## FAT
- FAT - File Allocation table
	- One of the first PC based systems (circa 1980)
-  FAT32 - File Allocation Table
	- Larger (2 TB) volume sizes
	- Maximum file size of 4 gb
- exFAT - Extended File Allocation Table
	- Microsoft flash drive file system
	- Files can be larger than 4 gigabytes
	- Compatible across many operating systems
	- Windows, Linux, MacOS
## ext4
- Fourth extended file system
	- update to ext3
	- Commonly seen in Linux and AndroidOS
## Extended Files Systems
- High performance file system for Linuc
	- Supported in most linux distros
- Designed for scalability
	- Large scale computing and high speed processing
- Features for the enterprise
	- Support for large file system size
	- Built in journaling
	- Minimal fragmentation
## APFS
- Apple File System (APFS)
	- Added to macOS High Sierra
	- Also Included with iOS and iPadOS
- Optimized for solid state storage
	- Encryption, snapshots, increased data integrity

# Installing Operating Systems: 1.2
## Boot Methods
- USB storage
	- USB must be bootable
	- Computer must support booting from USB
- Network boot
	- PXE ("Pixie") - Preboot eXecution Environment
	- Perform a remote network installation
	- Computer must support booting with PXE
- Solid state drives / Hard drives
	- Store many OS installation files
- Internet-based
	- Linus distibutions, macOS Recovery installation, Winsows updates
- External / hot swappable drive
	- some external drives can mount an ISO image (optical drive image)
	- Boot from USB
- Internal hard drive
	- Install and boot from separate drive
	- Create and boot from new partition
- Multiboot
	- Pick from two or more OSes from a boot menue
	- Windows, Linus, etc

## Types of installations
- Clean install
	- Wipe the slate clean and reinstall
	- Migration tool can help
- In place upgrade
	- Maintain existing applications and data
- Image deployment
	- Deploy a clone on every computer
	- Relatively quick
	- Can be completely automated
- Remote network installation
	- Local server or shared drive
	- Install across the internet
- Recovery partition
	- Hidden partition with installation files
- Repair installation
	- Fix problems with the Windows OS
	- Does not modify user files
- Other considerations
	- Load alternate third party drivers when necessary
		- Disk controller drivers, etc
## Zero Touch Deployment
- An automatic install
	- Streamlined implementation
- Customize the installation process
	- Automate the entire process
	- Company specific configurations
- A seamless user experience
	- Turn on the system and go
	- No domain questions or account issues
- Send a laptop to a user anywhere
	- The installation takes care of itself
## The disk partition
- Separates the physical drive into logical pieces
	- Useful to keep data separated
	- Multiple partitions are not always necessary
- Useful for maintaining separate operating systems
	- Windows, Linux, etc
- Formatted partitions are called volumes
	- Microsoft's nomenclature
## GPT partition style
- GPT (DUID Partition Table)
	- Globally Unique Identifier
	- The latest partition format standard
- Requires a UEFI BIOS
	- Can have up to 128 partitions
	- Maximum partition size is over 9 billion TB
	- Windows max partition is currently 256 TB
- No need for extended partitions or logical drives
## MBR Partition Style
- Master Boot Record
	- The old standby with old limitations
	- Maximum partition size of 2 TB
- Primary
	- Bootable partitions
	- Maximum of four primary partitions per storage drive
	- One of the primary partitions can be marked as Active
- Extended
	- Used for extending the maximum number of partitions
	- One extended partition per storage device (optional)
	- Contains additional logical partitions
	- Logical partitions inside an extended partition are not bootable

## Disk Partitioning
- The first step when preparing diskd
	- May already be partitioned
		- Existing partitions may not always be compatible with your new operating system
- An MBR style hard disk can have up to four partiions
- GUID partition tables support up to 128 partitions
	- Requires UEFI BIOS or BIOS-compatibility mode
	- BIOS-compatibility mode disables UEFI SecureBoot
- **BE CAREFUL**
	- Serious potential for data loss
	- This is not an every day occurrence

## Installation Partitioning

![[Pasted image 20260518132919.png]]

## Quick Format vs. Full Format
- Quick format
	- Creates a new file table
	- Looks like data is erased, but it's not
	- No additional checks
- Quick format is the default during installation in Windows 10 and 11
	- Use diskpart for a full format
- Full Format
	- Writes zeroes to the whole disk
	- Data is unrecoverable
	- Checks the disk for bad sectors (Time consuiming)
# Upgrading Windows: 1.2
## Why upgrade?
- Why upgrade?
	- Upgrade - Keep files in place
	- Install - Start over completely fresh
- Maintain consistency
	- Customized configurations
	- Multiple local user accounts
- Upgrades save hours of time
	- Avoid application reinstall
	- Keep user data intact
	- Keep user settings
	- Get up and running quickly
## Upgrade methods
- In place upgrade
	- Upgrade existing OS
	- Keeps all applications, documents, and settings
	- Start the setup from inside the existing OS
- Clean install
	- Wipe everything and reload
	- Backup your files
	- Start the setup by booting from the installation media
## Prepare the boot drive
- Know your drive
	- Is data on the drive?
	- Has the drive been formatted?
	- What partitions are on the drive
- Backup any old data
	- You may need that data again somedday
	- Save user preferences
- Most partitioning and formatting can be completed during the installation
	- Clear the drive and start fresh

## Before the installation
- Check minimum OS requirements
	- Memory, disk space, etc
	- And the recommended requirements
- Run a hardware compatibulity check
	- Runs when you perform an upgrade
	- Run manually from them Windows setup screen
	- PC Health Check for Windows 11
- Plan for installation questions
	- Drive/Partition configuration, license keys, etc.
- Application and driver compatibility
	- Check with the app developer and hardware manufacturer
## Windows product life cycle
- Quality updates
	- Monthly security updates and bug fixes
- Features updates
	- Annual update with new features
	- Used to occur every 3 to 5 years
- Support is provided after the release
	- 18 to 36 months
	- Dependent on the Windows version and edition
- Also called the Modern Lifecycle Policy
	- For continuously supported products

## Windows 11 hardware requirements
- Some additional requirements
	- More than usual
	- May require some planning
- TPM - Trusted Platform Module
	- Security hardware on the motherboard
	- Must be 2.0 compatible
	- Used for BitLocker, Windows Hello
- Check your hardware
	- Run tpm.msc
- UEFI BIOS
	- The hardware must be Secure Boot capable
- Enable Secure Boot for Additional Security
	- Check in System Information/System Summary
- May not be available on legacy systems
	- Check with the PC Manufacturer

![[Pasted image 20260519070820.png]]
# An Overview of Windows - 1.3
