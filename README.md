# OldDriverProtocol
老司机协议是用于即时聊天中老司机开车的协议标准

##How to use ODP(Old Driver Protocol)?

###As Old Driver
Use the Old Driver Protocol Standard to encode your resource link, and send the encoded plain text to others
###As Driving Beginner
When you recieve a mystery plain text from the Old Drivers, use the Old Driver Protocol to decode the encoded plain text, and you get the resource.
###As Passengers
Use the Old Driver Protocal to look for, or to request resource from those real old drivers

##History
2015.12.30: v0.1 protocol standard release
2015.12.27: First presented in ACG Hackers QQ Group

#ODP Standard v0.2
###0. Requirement
The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in RFC 2119

The following signs are used to adjunctively describe the structure inside of a format declaration
*  [argument] : represents that the argument is OPTIONAL
*  (argument) : represents that the argument is a tag or another meaningful expression
*  {1-10} : represents that the argument MUST be in the declared range. `i.e. from 1 to 10`
*  arg1|arg2 : represents that either arg1 or arg2 is acceptable `i.e. [a|b] represents that either a or b, or empty is valid`


###1. Terminology
`ODP Header`

An Old Driver Protocol Message Structure's Begin Tag.

*Requirement Level: MUST*

*Format: ODP/(ODPversion) \[(Operation)\]*

*Operations:DRIVING,REQUEST,PREVIEW*

*e.g. ODP/0.2 DRIVING*

`Resource Type`

The statement of the resource type which this ODP Message contains.


*Requirement Level: OPTIONAL* 

*Format: Type/(ResourceType)*

*ResourceTypes: NetDisk, PlainText, Image, URI(RFC 3305), MIME(RFC 2045, RFC 2046, RFC 2047, RFC 2048, RFC 2049, etc.)*

*e.g. Type/NetDisk*


`ODP Content`

The Content of Resource. **An empty line before it is Required**.

*Requirement Level: MUST*

*Format: (ResourceContent) | ShousaiKibou*

*e.g. http://pan.baidu.com/xxxx*

*p.s. The content can be a single image without type declaraion when PREVIEW defined in header*


`ODP Ending`

Marks that ODP Message ends.

*Requirement Level: RECOMMENDED*

*Format: ODP/END*


###2. Message Content Structure
Example:

ODP/0.1**\r\n**

Type/NetDisk**\r\n**

**\r\n**

http://pan.baidu.com/xxxx
