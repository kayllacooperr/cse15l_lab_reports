## Lab #3
*May 10, 2023*

> Part 1: Research Commands

This lab report is going to focus on the `grep` command and how different command-line options can prove useful.
For all in-line command arguments, I used the [official grep documentation](https://www.gnu.org/software/grep/manual/grep.html#Introduction),
which shows all possible command-line options, their uses, along with a short explanation/examples when necessary.

> `grep -c`

```
$ grep -c "takeoff" chapter-1.txt
3
```
```
$ grep -c "aircraft" chapter-1.txt chapter-2.txt
chapter-1.txt:121
chapter-2.txt:1
```

The `-c` command will return the number of lines that contain the desired word, rather than just printing out 
the lines themselves. This is extremely useful for word count purposes rather than having to read through all the
lines given by the output. Furthermore when given multiple files, the output will specify which files contain the 
desired phrase, rather than grouping all the file counts together.

> `grep -L`

```
$ grep -L "RNA" 1468-6708-3-1.txt 1471-213X-1-1.txt rr37.txt        
1468-6708-3-1.txt
rr37.txt
```

```
$ grep -L "infection" ar799.txt bcr45.txt cc3.txt
cc3.txt
```

The `-L` command will print all files that do not have a match for the given input. In this case, "RNA" and "infection"
were not found in 2/3 and 1/3 of their respective files. This would be extremely useful if you needed to search for
files while avoiding a certain phrase or topic.

. `grep -m <number>`

```
$ grep -m 5 "treatment" DraftRecom-PDF.txt Session2-PDF.txt
DraftRecom-PDF.txt:treatment strategy, "Screening, Brief Intervention, and
DraftRecom-PDF.txt:mean sending a patient to a specialized treatment facility.
DraftRecom-PDF.txt:Larry Gentilello asserted that effective treatments already
DraftRecom-PDF.txt:exist, not just treatments that "hold promise." The "promise" has
DraftRecom-PDF.txt:be made less tentative: for example, "treatments that work should
Session2-PDF.txt:lead naturally to referral and treatment. Others may not promote
Session2-PDF.txt:referral and treatment. Much of the screening literature is
Session2-PDF.txt:in ED environments that have treatment available, an adequate
```

```
$ grep -m 1 "drinking" Session4-PDF.txt
to moderate their drinking when compared with those who did not
```

The `-m <number>` command will only show a certain number of matches depending on the 
integer value given after the `-m` command. When given multiple files, the output will 
show the number of matches per file, as opposed to the number of matches over all files combined. 
For example, the first example shown resulted in 5 matches for "treatment" in DraftRecom-PDF.txt 
and 3 in Session2-PDF.txt, rather than just 5 matches overall. This proves useful to limit the output to
something legible. For instance, if you were searching a series of .txt files which all related to biology
and you wanted to search for "DNA", it would be extremely helpful to limit the output to around 10-15 times,
or else the terminal will be overrun with lines containing "DNA".

> `grep -y`

```
$ grep -y "scientific" journal.pbio.0020001.txt
        the world scientific community closer to each other (Annan 2003). Mr. Annan stressed the
        countries, asserting that “This unbalanced distribution of scientific activity generates
        serious problems not only for the scientific community in the developing countries, but for
        several scientists, who present overwhelming evidence for the disparity in scientific
        Goldemberg 1998; Riddoch 2000). For example, recent United Nations Educational, Scientific,
        developed countries accounted for some 84% of the global investment in scientific research
        88% of all scientific and technical publications registered by the Science Citation Index
        (SCI). North America and Europe clearly dominate the number of scientific publications
            North America and Europe clearly dominate the number of scientific
        2001). But is the disparity in scientific contributions between the developed and
        respectively, only 1.8% and 2% of scientific publications worldwide, have increased the
        (26%). The percentage of global scientific publications from North America actually
        Using the SCI databases produced by the Institute for Scientific Information (ISI), as
        (RICYT), we examined the differences in the number and proportion of scientific
        only 5.45% to the total number of scientific publications in these ten years (RICYT
        assessing scientific productivity or technical advances (May 1997). More relevant
        1990 as a comparison, revealed that scientific publishing in Latin America increased the
        Other relative indicators of scientific productivity, such as the number of publications
        21% of the amount invested in United States (RICYT 2002). Indeed, this scientific
        of its resources in scientific research and development. Latin American investment in
        One potential explanation for the increase in scientific productivity in Latin America
        is that scientific development during the 1990s was particularly strong for many countries
        measure of scientific productivity is becoming more important in Latin America. Increased
        scientific collaborations among scientists in Latin America, Europe, and the United States
        United States could reflect a trend towards more costly research in larger scientific
        Scientific Impact from Latin America
        scientific community? We used SCI 2001 data to examine the proportion of publications in
        the scientific output in the field of ecology in Latin America is having a relatively low
        impact in the international scientific community and is underrepresented in the top
        Although there are outstanding scientific researchers in the developing world who
        independently are making important contributions to the international scientific community,
        scientific mainstream of the developed regions. This is not to suggest any sort of
        introducing novel research findings in multiple scientific forums. Funding these
        The positive trends in scientific productivity in Latin America should not be
        Annan. There are many compelling reasons for the push to increase scientific input from the
        dominated by two geographic regions. Many scientific problems could be solved much more
        readily with the cooperation and scientific insight of scientists from developing regions.
        Climate change and biodiversity research, for example, urgently need the scientific input
        areas of concern that are having a proportionally greater scientific and social impact upon
        themselves scientific innovations that can greatly advance the knowledge of the rest of the
            Climate change and biodiversity research urgently need the scientific
        developing countries contribute a more equitable share to the international scientific
        direction. The extremely high scientific productivity of many developing nations, corrected
        publications as a measure of scientific output, particularly if these publications can
```

```
$ grep -y "as" journal.pbio.0020010.txt
        JSTOR is successful for reasons its founders did not intend. Bill Bowen's inspired
        vision was of a solution to libraries' ever-voracious demands for space to house paper
        volumes. The idea was that libraries could save space by removing volumes available in
        important journal runs JSTOR has digitised. Paper holdings have not decreased dramatically,
        but electronic holdings have increased. So a space-saving service became an access
        As an access service, JSTOR is a creation of its time. Understandable though the
        Likewise, the decision to digitise the back-runs of around 100—now 218—paper journals was a
        hundred titles. Its technical solutions and financial models look dated as both
        subscription-based and open-access publishers improve their services to authors and to
        readers. As the number of journal articles accessible over the networks increases, JSTOR
        will be seen as a small-scale pioneer from which we learned valuable lessons.
        funding to launch any such initiative has to be accompanied by a sound business plan to
        ensure long-term economic viability. JSTOR has achieved that transition, and its success
        publishing communities to buy into a product that was only a promise. Meeting user needs
        for easy access to high-quality content was the key to the fulfilment of that promise.
        JSTOR's public image is of quality in depth—long runs of core journals—and that image has
        to become the hallmark of the new open-access initiatives as they develop.
        financial planning had in coming to terms with consortial purchases delayed its growth as
        access and therefore securing longer-term financial stability (as the major publishers have
        adaptation of the JSTOR purchasing model for selling outside the United States, the United
        Kingdom being the exception. The UK deal was with JISC, the Joint Information Systems
        Committee of the UK Higher Education Funding Councils, acting more as a negotiating agent
        to be imaginative. For all vendors, there has to be an understanding of the political,
        publishing has combined with the globalisation of the networks and with the globalisation
        readily than in the traditional subscription-based journals.
        to JSTOR as it is today. There is so much detail in the book that the reader may feel that
        by my institution, University College London, in joining JSTOR before the JISC deal was
        that outside the United States, as well as within, the early interest in JSTOR came from
        been just as valuable?
        Leaving aside quibbles and caveats about the book and about JSTOR, this remains a
        fascinating and instructive history of an important and ground-breaking initiative. Bill
        has not gone away in the ten years since JSTOR was conceived, but the ultimate solution—the
        availability of electronic content—has become closer, and JSTOR's success has encouraged
        has been achieved since 1993, what promise is held out by the next ten years'!
```

Apologies for the long outputs, but that's all thanks to the `-y` command! `-y` will allow grep to bypass
case distinctions, allowing for more output. This is extremely useful for finding words/phrases in a file,
despite if they are the first word in the sentence, or if the word is refering to a proper noun, and other
similar cases. Now upper/lower cases will both be shown by grep when using the `-y` command.
