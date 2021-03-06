# Best Practices for Building AMIs<a name="best-practices-for-building-your-amis"></a>

All AMIs built and submitted to AWS Marketplace must adhere to all product policies\. To share your AMI and verify that it meets all AWS Marketplace requirements, use the self\-service [AMI scanning tool](https://aws.amazon.com/marketplace/management/manage-products/#/manage-amis.unshared)\. The following are some best practices and references to help you build AMIs\.

## Rights<a name="rights"></a>

You are responsible for securing resell rights for non\-free Linux distributions, with the exception of AWS\-provided Amazon Linux, RHEL, SUSE, and Windows AMIs\.

## Building an AMI<a name="building-an-ami"></a>
+ Ensure that your AMI meets all AWS Marketplace policies, including disabling root login\. 
+ Create your AMI in the US East \(N\. Virginia\) Region\. 
+ Create products from existing, well\-maintained AMIs backed by Amazon EBS with a clearly defined life cycle provided by trusted, reputable sources such as AWS Marketplace\. 
+ Build AMIs using the most up\-to\-date operating systems, packages, and software\. 
+ All AMIs must start with a public AMI that uses hardware virtual machine \(HVM\) virtualization and 64\-bit architecture\. 
+ Develop a repeatable process for building, updating, and republishing AMIs\. 
+ Use a consistent OS username across all versions and products\. We recommend **ec2\-user**\.
+ Configure a running instance from your final AMI to the end\-user experience you want and test all installation, features, and performance *before* submission to AWS Marketplace\. 
+ Ensure that for Linux\-based AMIs that a valid SSH port is open \(default is 22\) and for Windows\-based AMIs that an RDP port is open \(default is 3389\)\. WINRM \(port 5985\) must be open to 10\.0\.0\.0/16\. 

 Resources:

 [Creating Your Own AMI](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide//AMIs.html#creating-an-ami) in the *Amazon EC2 User Guide for Linux Instances*

 [Creating a Custom Windows AMI](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AMIs.html) in the *Amazon EC2 User Guide for Windows Instances* 

 [Creating an Instance Store\-Backed Linux AMI](Amazon EC2 User Guide for Linux Instances/creating-an-ami-instance-store.html) in the *Amazon EC2 User Guide for Linux Instances* 

 [How do I create an Amazin Machine Image \(AMI\) from an EBS\-backed Windows instance?](https://aws.amazon.com/premiumsupport/knowledge-center/create-ami-ebs-backed-windows/) 

 [Amazon Linux AMI](https://aws.amazon.com/amazon-linux-ami/) 

 [Linux Forums](http://www.linuxforums.org/) 

 [Amazon EC2 Instance Types](http://aws.amazon.com/ec2/instance-types/) and [Instance Types](http://docs.amazonwebservices.com/AWSEC2/latest/UserGuide/instance-types.html?r=2153) 

## Securing an AMI<a name="securing-an-ami"></a>
+ Architect your AMI to deploy as a minimum installation to reduce the attack surface\. Disable or remove unnecessary services and programs\. 
+ Whenever possible, use end\-to\-end encryption for network traffic\. For example, use Secure Socket Layer \(SSL\) to secure HTTP sessions between you and your customers\. Ensure that your service uses only valid and up\-to\-date certificates\. 
+ Use security groups to control inbound traffic access to your instance\. Ensure that your security groups are configured to allow access only to the minimum set of ports required to provide necessary functionality for your services\. Allow administrative access only to the minimum set of ports and source IP address ranges necessary\. 
+ Consider performing a penetration test against your AWS computing environment at regular intervals; or, consider employing a third party to conduct such tests on your behalf\. For more information, including a penetration\-testing request form, see [AWS Penetration Testing](http://aws.amazon.com/security/penetration-testing/)\. 
+ Be aware of the top 10 vulnerabilities for web applications and build your applications accordingly\. To learn more, visit [Open Web Application Security Project \(OWASP\) \- Top 10 Web Application Security Risks](https://www.owasp.org/index.php/Category:OWASP_Top_Ten_Project)\. When new Internet vulnerabilities are discovered, promptly update any web applications that ship in your AMI\. Examples of resources that include this information are [SecurityFocus](http://www.securityfocus.com/vulnerabilities) and the [NIST National Vulnerability Database](http://nvd.nist.gov/)\.

 Resources:
+  [AWS Cloud Security](http://aws.amazon.com/security/) 
+  [The Center for Internet Security \(CIS\): Security Benchmarks](http://benchmarks.cisecurity.org/downloads/benchmarks/) 
+  [The Open Web Application Security Project \(OWASP\): Secure Coding Practices Quick Reference Guide](https://www.owasp.org/index.php/OWASP_Secure_Coding_Practices_-_Quick_Reference_Guide) 
+  [OWASP Top 10 Web Application Security Risks](https://www.owasp.org/index.php/Category:OWASP_Top_Ten_Project) 
+  [SANS \(SysAdmin, Audit, Networking, and Security\) Common Weakness Enumeration \(CWE\) Top 25 Most Dangerous Software Errors](http://www.sans.org/top25-software-errors/) 
+  [Security Focus](http://www.securityfocus.com/vulnerabilities) 
+  [NIST National Vulnerability Database](http://nvd.nist.gov/) 