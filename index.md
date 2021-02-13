## Welcome to the futures contract system for transactions and documentation



The project contains the necessary repositories to execute the transactions, document them in the ledger and obtain a copy of the contract authenticated by the contracting parties within the framework of the deal.


### Structure

The infrastructure that provides rapid and secure access to important documents is a basic requirement in the field of contracts, so that the paragraphs can be found in one place and in a unified manner that ensures that the terms of the agreements are not tampered with.
```markdown
using System;
using System.IO;
using System.Security.Cryptography;

public class EncryptExample
{
    public static void Main(string[] args)
    {
        //Encryption key used to encrypt the stream.
        //The same value must be used to encrypt and decrypt the stream.
        byte[] key = { 0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16 };

        try
        {
            //Create a file stream
            using FileStream myStream = new FileStream("TestData.txt", FileMode.OpenOrCreate);

            //Create a new instance of the default Aes implementation class  
            // and configure encryption key.  
            using Aes aes = Aes.Create();
            aes.Key = key;

            //Stores IV at the beginning of the file.
            //This information will be used for decryption.
            byte[] iv = aes.IV;
            myStream.Write(iv, 0, iv.Length);

            //Create a CryptoStream, pass it the FileStream, and encrypt
            //it with the Aes class.  
            using CryptoStream cryptStream = new CryptoStream(
                myStream, 
                aes.CreateEncryptor(),
                CryptoStreamMode.Write);

            //Create a StreamWriter for easy writing to the
            //file stream.  
            using StreamWriter sWriter = new StreamWriter(cryptStream);

            //Write to the stream.  
            sWriter.WriteLine("Hello World!");

            //Inform the user that the message was written  
            //to the stream.  
            Console.WriteLine("The file was encrypted.");
        }
        catch
        {
            //Inform the user that an exception was raised.  
            Console.WriteLine("The encryption failed.");
            throw;
        }
    }
}

```

Ensuring perfect encryption creates trust between contractors and facilitates establishing rights
### The mechanism
![image](https://raw.githubusercontent.com/2saveefor/Regulatory-Sandbox/main/Rest%20API%20Gateway.jpg)

Creating interconnectedness between services lends a logic that protects regulations and legislation and gives meaning to the concept of contracting.

### the aim

Finding providers is the building block for first-chain methods documenting the feasibility of contractor availability.
