Fuzzing is a dynamic application security testing technique that involves providing invalid, unexpected, or random data as inputs to a computer program. The goal is to discover bugs, crashes, or other vulnerabilities by observing how the program handles these inputs. 

ffuf (Fuzz Faster U Fool)
ffuf is a fast web fuzzer written in Go. It is widely used in the cybersecurity community for web application fuzzing. Here are some key aspects and features of ffuf:
Automated Exploration: Fuzzing automates the process of exploring the application by systematically generating and sending numerous test cases. By using wordlists, ffuf can generate a large number of HTTP requests to test various parts of a web application, such as directories, files, parameters, and headers.

Efficiency and Speed: Fuzzing needs to be fast and efficient to cover a wide range of inputs in a reasonable time. Written in Go, ffuf leverages the language's concurrency features to perform multiple HTTP requests in parallel, significantly speeding up the fuzzing process.

Flexibility and Customization: Different applications require different fuzzing strategies and configurations.ffuf provides various options for customizing the fuzzing process, such as specifying the request method (GET, POST), adding custom headers, following redirects, and filtering results based on response codes, size, or content.

#How to install fuff in kali linux:

Commmand: sudo apt-get install ffuf

<img width="403" alt="ffuf 2" src="https://github.com/Ashwatiycce/Ashwati/assets/140001632/60899d79-0b9b-4dd6-97ce-05cc513ab9e4">

Usage

With the command ffuf -h. We can find the help page we can explore the tool with this command.
<img width="549" alt="ffuf 3" src="https://github.com/Ashwatiycce/Ashwati/assets/140001632/affda177-fe4c-4f21-a1cf-c3edd4f5d61a">

ffuf offers many options for fuzzing.

To specify the position to be fuzzed, use the word "FUZZ" in the ffuf command.

Directory and File Discovery
You can find directories on a website with the following command. It uses the -w flag to provide a wordlist and the -u flag to specify the URL with "FUZZ" as the placeholder for fuzzing.

ffuf -w wordlist.txt -u http://website.com/FUZZ
<img width="483" alt="ffuf 4" src="https://github.com/Ashwatiycce/Ashwati/assets/140001632/49a62ed4-388e-4358-8208-0857be925d44">

Example Commands:
1. Discovering Hidden Directories
ffuf -u http://testphp.vulnweb.com/FUZZ -w /usr/share/wordlists/dirb/common.txt
Description: This command tests for common directories on the example vulnerable site testphp.vulnweb.com using a wordlist of common directory names.
<img width="434" alt="ffuf 1" src="https://github.com/Ashwatiycce/Ashwati/assets/140001632/97147a9a-5a16-465d-8f41-4c144607ce35">

2. Finding Hidden Parameters
ffuf -u http://testphp.vulnweb.com/artists.php?FUZZ=test -w /usr/share/wordlists/seclists/Discovery/Web-Content/burp-parameter-names.txt
Description: This command attempts to discover hidden GET parameters on the artists.php page by replacing FUZZ with different parameter names from the wordlist.
<img width="467" alt="ffuf 5" src="https://github.com/Ashwatiycce/Ashwati/assets/140001632/8a147254-1f7f-400f-b877-87aaff42a72b">

3. Testing for Sensitive Headers
ffuf -u http://testphp.vulnweb.com/ -H "FUZZ: value" -w /usr/share/wordlists/seclists/Discovery/Web-Content/burp-headers.txt
Description: This command fuzzes HTTP headers to see how the server responds to different headers from the wordlist.
<img width="407" alt="ffuf 6" src="https://github.com/Ashwatiycce/Ashwati/assets/140001632/a58e335c-4e64-46f3-bc78-3b01958d906d">

4.Recursive Directory Fuzzing
ffuf -u http://testphp.vulnweb.com/FUZZ -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -recursion -recursion-depth 2
Description: This command performs recursive fuzzing to find nested directories up to a depth of 2.
<img width="608" alt="ffuf 7" src="https://github.com/Ashwatiycce/Ashwati/assets/140001632/8cc35ba2-357e-443a-8774-ac3a0219b76e">





