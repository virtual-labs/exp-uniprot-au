1.	Follow (https://vlab.amrita.edu/index.php?sub=3&brch=311&sim=1835&cnt=2) to install R in personal computer.
2.	Install the SeqinR package.
3.	To load “SeqinR” R package follow > library("seqinr") 
4.	Follow the code in the command window: 

        retrieveseqs<- function(seqnames,acnucdb) #custom function for retrieving multiple sequence from Uniprot
    
        {
        myseqs<- list()
        # Make a list to store the sequences
        require("seqinr") 
        choosebank(acnucdb)
        for (i in 1:length(seqnames))
        {
        seqname<- seqnames[i]
        print(paste("Retrieving sequence",seqname,"..."))
        queryname<- "query2"
        query<- paste("AC=",seqname,sep="")
        query_test<- query(queryname,`query`)
        seq<- getSequence(query_test$req[[1]]) # Makes a vector "seq" containing the sequence
        myseqs[[i]] <- seq
         }
        closebank()
        return(myseqs)
        }
        seqnames<- c("P06747", "P0C569", "O56773", "Q5VKP1")
        seqs<- retrieveseqs(seqnames,"swissprot")
        length(seqs)
        seq1 <- seqs[[1]]
        seq1
        seq2 <- seqs[[2]]
        seq2[1:20]
5.	Click Execute Button for output.    
&nbsp;

**Procedure to work simulator**
1.	Default FASTA files of multiple protein sequence were provided in R platform. 
2.	User can choose their required sequence and can load the sequence for Uniprot R analysis.
3.	From the graphical output interpret the detailed information of the selected sequences in terms of similarities, phylogeny analysis and so on. 
