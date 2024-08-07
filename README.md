# In this Azure lab, I learned how to create resources in Azure such as virtual machines andModified the network security groups (firewalls) of the machines to make them vulnerable.

<details><summary>Creating windows 10 VM</summary> 

![image](https://github.com/user-attachments/assets/382c44d5-5f89-4f06-94b4-e8813143374b)

![image](https://github.com/user-attachments/assets/e6e97a84-884f-4a92-b812-8f4d7ef56d97)

![image](https://github.com/user-attachments/assets/780a1864-ca2b-4897-98b1-cfadf8c6f5ef)

![image](https://github.com/user-attachments/assets/51fc8c36-a71d-4250-b231-3b4d88a0689c)

![image](https://github.com/user-attachments/assets/d33c54ee-7c64-4b3b-96f0-daf77a051731)

Now the machine is being created and deployed

![image](https://github.com/user-attachments/assets/45f56150-0fa3-4c3b-8961-e7c07a9c58eb)

</details>

<details><summary>Creating Linux VM</summary>

![image](https://github.com/user-attachments/assets/c164b5f6-4cd5-4e2a-acb9-3844dd48a6f5)

![image](https://github.com/user-attachments/assets/8a22ce62-5649-4c57-8ba4-d255367ec099)

![image](https://github.com/user-attachments/assets/fd216fc9-224d-41a7-88b7-701baa174adb)

![image](https://github.com/user-attachments/assets/946772dd-7e6f-4d55-9dc8-9de06a0b1535)

Verifying resource groups

![image](https://github.com/user-attachments/assets/fb558489-8a75-4ad2-a5cd-5d5741ab3f3f)
</details>

<details><summary>Modifying the NSG (Firewall) of the VMs</summary> <br>

The goal here is to open the VMs to the public internet.
To allow all traffic from the internet to go through, I deleted the RDP rule

![image](https://github.com/user-attachments/assets/efd53fa6-0b37-4297-86ea-b410c96706ee)

![image](https://github.com/user-attachments/assets/8fb12c98-aaf6-4487-9375-cd8eb0e46500)

Then, I added a new rule that allows all traffic from the public internet to come through.

![image](https://github.com/user-attachments/assets/34794f86-3895-4820-b7aa-6c1b553f7471)

![image](https://github.com/user-attachments/assets/d9a312c9-4d9d-4f44-b94f-262180fb5a07)

Same procedure for the Linux VM. Deleted SSH rule and added another rule that
allows all traffic to come through.

![image](https://github.com/user-attachments/assets/306eee44-475b-4412-b3b7-6f73bc1e31e8)


![image](https://github.com/user-attachments/assets/2321de66-b8ec-4640-8f34-a88b49f6cc32)

</details>

<details><summary>Creating an attack VM to generate some logs</summary> <br>

  Logging is an essential component of cybersecurity operations. Without proper logging, it can be difficult or impossible to identify and respond to security incidents. 
  <br><br>Logging allows organizations to track activity on their networks and systems.<br><br>
  In this Lab, I will create a third virtual machine that will be used to do some actions (attacks) against the other two VMs. I will attempt to log into the SQL server from the attack VM, log into the windows VM. 

  ![image](https://github.com/user-attachments/assets/c22ce68c-1316-46b1-a64d-ef9906a1f2d0)

  ## Create the attack VM

  ![image](https://github.com/user-attachments/assets/0824878b-d3f8-4403-b5ad-ca9fcaa89cb2)

  ![image](https://github.com/user-attachments/assets/d060ee9c-1a3f-42db-b167-eb97ce9656fe)

  Here are the three VMs

  ![image](https://github.com/user-attachments/assets/009f73bd-8335-486e-8d8e-4ebfb9c0ee59)

  ## Generate some failed RDP logs against “windows-vm”

  From within of “attack-vm”, attempt to RDP into “windows-vm” with the wrong credentials a few time

  ![image](https://github.com/user-attachments/assets/39f990e4-7bc5-44e7-92ed-a9504438dfe2)

  
## Generate some failed MS SQL Auth logs against “windows-vm”

Still within “attack-vm”, install SSMS and attempt to connect to the SQL Server on “windows-vm” with a bad password

![image](https://github.com/user-attachments/assets/d1a0c58a-1d2b-4e88-89bb-90b6ed8d189e)

## Generate some failed SSH logs against “linux-vm”

![image](https://github.com/user-attachments/assets/e6cbfb5c-ae02-4675-904f-0abd61d855ee)

  
</details>

<details><summary>Reviewing the logs generated from last step</summary> <br>

## Now that we attacked the two VMs from the attack VM, It is time to RDP back into the normal windows VM and view the logs (Security log for RDP, Application log for SQL)

![image](https://github.com/user-attachments/assets/53d35afb-b76d-48ec-ab61-d3045c2ea800)

![image](https://github.com/user-attachments/assets/e7b97f61-7fd5-404a-96ea-e2e49161f45f)

## SSH into the Linux VM, observe the logs

![image](https://github.com/user-attachments/assets/fe72fc9c-ccbb-4861-8ae7-f4b230cb44fa)


![image](https://github.com/user-attachments/assets/33f8ca51-4053-4409-ae2f-74acf30ad56f)




</details>











