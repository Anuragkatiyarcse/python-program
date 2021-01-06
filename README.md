# python-program
1: Write a Python program to read a file line by line and store it into a list.
program
def file_read(filename):
        with open(filename) as file:
               
                content_list = file.readlines()
                print(content_list)
file_read(\'test.txt\')

output:- 
['Welcome to w3resource.com.\n', 'Append this text.Append this text.Append this text.\n', 'Append this text.\n
', 'Append this text.\n', 'Append this text.\n', 'Append this text.\n'] 


2: Write a Python program to calculate the number of days between two dates. Sample dates : (20200702), (20200711)
Program

from datetime import date
first_date = date(2014, 7, 2)
last_date = date(2014, 7, 11)
delta = last_date - first_date
print(delta.days)

ouput:- 9 

3: Write a Python program to convert the Python dictionary object (sort by key) to JSON data. Print the object members with indent level 4.
Program:

import json
j_str = {'4': 5, '6': 7, '1': 3, '2': 4}
print("Original String:")
print(j_str)
print("\nJSON data:")
print(json.dumps(j_str, sort_keys=True, indent=4))

output:- 
Original String:
{'4': 5, '6': 7, '1': 3, '2': 4}

JSON data:
{
    "1": 3,
    "2": 4,
    "4": 5,
    "6": 7
}

4. Write a Python program to sort a list of dictionaries using Lambda. Original list of dictionaries : [{'make': 'Nokia', 'model': 216, 'color': 'Black'}, {'make': 'Mi Max', 'model': '2', 'color': 'Gold'}, {'make': 'Samsung', 'model': 7, 'color': 'Blue'}] Sorting the List of dictionaries : [{'make': 'Nokia', 'model': 216, 'color': 'Black'}, {'make': 'Samsung', 'model': 7, 'color': 'Blue'}, {'make': 'Mi Max', 'model': '2', 'color': 'Gold'}]

Program:

models = [{'make':'Nokia', 'model':216, 'color':'Black'}, {'make':'Mi Max', 'model':'2', 'color':'Gold'}, {'make':'Samsung', 'model': 7, 'color':'Blue'}]
print("Original list of dictionaries :")
print(models)
sorted_models = sorted(models, key = lambda x: x['color'])
print("\nSorting the List of dictionaries :")
print(sorted_models)

output:- 
Original list of dictionaries :
[{'make': 'Nokia', 'model': 216, 'color': 'Black'}, {'make': 'Mi Max', 'model': '2', 'color': 'Gold'}, {'make': 'Samsung', 'model': 7, 'color': 'Blue'}]

Sorting the List of dictionaries :
[{'make': 'Nokia', 'model': 216, 'color': 'Black'}, {'make': 'Samsung', 'model': 7, 'color': 'Blue'}, {'make': 'Mi Max', 'model': '2', 'color': 'Gold'}]

5. Write a Python program that takes a text file as input and returns the number of words of a given text file.
Program:

def count_words(filepath):
   with open(filepath) as f:
       data = f.read()
       data.replace(",", " ")
       return len(data.split(" "))
print(count_words("words.txt"))
output:- 
Append this text.



6: Write a Python program to convert an array to an array of machine values and return the bytes representation.
Program:

from array import *
print("Bytes to String: ")
x = array('b', [1, 2, 3, 4, 5, 6])
s = x.tobytes()
print(s)
output:- 
Bytes to String:                                                       
b'python programming'


8. Program to Generate random logs and write in a file , once the file size reaches 2Mb open new file and continue writing
Program:

import random
def random_line(fname):
    lines = open(fname).read().splitlines()
    return random.choice(lines)
print(random_line('test.txt'))
output: -45


9. Script to ping and check whether any given IPs are active, also whether given set of software are installed in the existing system ( like java, kubectl, aws etc)
Answer: 
Verify that the aws-node pod is in Running status on each worker node
To verify that the aws-node pod is in Running status on a worker node, run the following command:
kubectl get pods -n kube-system -l k8s-app=aws-node -o wide

To verify that the API server endpoint of your Amazon EKS cluster can be reached by the worker node, run the following command:
curl -vk https://eks-api-server-endpoint-url
    To verify that the kube-proxy pod is in Running status on each worker node, run the following command:
kubectl get pods -n kube-system -l k8s-app=kube-proxy -o wide
.    Verify that your worker node can access API endpoints for Amazon EC2, Amazon ECR, and Amazon S3.
Note: You can configure these services through public endpoints or AWS PrivateLink.
Verify that your subnet has enough free IP addresses available
To list available IP addresses in each subnet in the Amazon Virtual Private Cloud (Amazon VPC) ID, run the following command:
aws ec2 describe-subnets --filters "Name=vpc-id,Values=<VPCID>" | jq '.Subnets[] | .SubnetId + "=" + "\(.AvailableIpAddressCount)"'
The available-ip-address-count should be greater than 0 for the subnet where pods are launched.
Verify that you're running the latest stable version of the CNI plugin

