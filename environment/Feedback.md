first classroom feedback: 
 * out of three options, docker, which was optional one, became the main alternative for paper reproduction. 
 * correction to run command to remove -d parameter
 * no complete understand how docker workded: I was happy to see it working on windows, till then I though I would have to find out a new image only for windows.
 * teachers comment: changed manual parameter´s tunning to automated GridSearch

second classroom feedback:
* code failed because updates for gridsearch didn´t work properly with sckit-learn 0.17, and ntlk 3.1. Both had to be
upgraded to 0.18 and 3.2 respectively and a new image was created.
* new branch: old cold for manual parameter was partially lost, I should have created a new branch to hold the new changes.
* virtual machine was big, around 4GB, and this caused an issue. I then reduced the size to 2.5GB by not installing third party softwares.
* included citations on text and references were automatically generated.
* codes in paper were moved to other documents and imported results.

third classroom feedback:
* docker was also tested on MAC, and it was reproduced successfully by Mariana.
* reproduction steps were updated and it was included new steps for MAC OS
* improved explation on some sections such as introduction, dataset, third party libraries
* adaptation of script to generate pdf with automated references.



