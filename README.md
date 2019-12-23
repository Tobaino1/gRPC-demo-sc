# gRPC-demo-server and client
 Simple gRPC server and client
 
 -------- Oyekan Oluwatobi -------- 12/23/2019
***************************""""""""""""""""""""""""""""""""""""""############

gRPC client-server application with C# and dotnet core.

Infrastructure of the folder structure:

Root folder
GrpcServer (dotnet core console app)
GrpcClient (dotnet core console app)
Message (dotnet core class lib)
gencert.bat (bash script to generate ssl certificates)

certificate is derived either from (https://stackoverflow.com/a/37739265/6089658) or the use of OpenSSL tool to generate self-signed certificates (OpenSSL installer from https://slproweb.com/products/Win32OpenSSL.html)

The OpenSSL installer resides at c:\OpenSSL-Win64\ (just to match up /  to update the 3rd line of the script so it conforms with the location of the config file)


***************************""""""""""""""""""""""""""""""""""""""############

Generation of certificates from Powershell window in the same folder as gencert.bat file  takes place by executing --->>> .\gencert.bat

it produces 8 new files (two for the certificate authority, three for client certificate, three for server certificate, Visual Studio solution with projects)

Then a new visual studio solution in the root folder (that's the same path as gencert.bat) is created with the following additions of .Net Core projects:

Message (Class Library)
GrpcServer (Console App)
GrpcClient (Console App)

GrpcServer project (contains the data folder which houses the json file that has sample feeds (which were generated from generatedata.com/)
and it also contains the newly created folder named Certs where certificate authority and server certificate files are copied to)
GrpcClient project (contains newly created folder named Certs where certificate authority and server certificate files are copied to)
In Message project, a file named messages.proto was created to give insight about the structure of the data. 
There is a need to install Google.Protobuf, Grpc and Grpc.Tools nuget packages.

