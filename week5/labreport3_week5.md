## Part1

For reversed(int[] arr) method in ArrayExamples.java:

A failure-inducing input for the buggy program: 
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }

@Test public void testReversed1() { 
    int[] input1 = {3,4,5}; 
    assertArrayEquals(new int[]{5,4,3}, ArrayExamples.reversed(input1)); 
    } 
```
The result is: Expected [5] but was [0]

An input that doesn’t induce a failure:
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }

@Test
  public void testReversed2() {
    int[] input1 = {};
    assertArrayEquals(new int[]{}, ArrayExamples.reversed(input1));
  }
```

Symptom:
<img width="1024" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/2e5ebd60-7fde-4e36-b2d2-35304742f741">


The bug:
The bug in the reversed() method is that it creates a new array without assigning new elements to it and the for loop updates the original array with default value in the new array, which is the opposite of what we want. 

Before:
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
After:
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```
As mentioned, the problem is that we are updating the original array by using the default values from the newArray and we return the original array.
However, the method means to create a new array and update the value of this new array by reversely looping through elements in the original array. We want to return the newArray eventually.

So I changed the assigning value part in the for loop from ```arr[i] = newArray[arr.length - i - 1];``` to ```newArray[i] = arr[arr.length - i - 1];```, and return newArray instead of arr. By this, we are updating the value in the newArray. 


## Part2
### 1
```
(base) conggexu@Congges-MacBook-Pro technical % grep -r "reformulation"
./plos/journal.pbio.0020147.txt:        important addition to evolutionary theory” but “requires a reformulation of evolutionary
./biomed/1476-069X-2-9.txt:        redesigns, product reformulations, and material
```
```grep -r "reformulation"``` recursively finds all the lines in the files in the directory and subdirectories containing the string "reformulation" This is case sensitive to the string input and it can be helpful when we want to find all the files that talks about reformulation across different categories(plos, biomed, 911report, etc.)

```
(base) conggexu@Congges-MacBook-Pro technical % grep -r "Bill Clinton" 
./plos/journal.pbio.0020054.txt:        controlled or “prescribed” burning (Figure 2). During Bill Clinton's administration,
./plos/pmed.0020035.txt:        In 1997, United States President Bill Clinton announced the challenge to develop an AIDS
./911report/chapter-13.4.txt:                Bin Laden: How Bill Clinton's Failures Unleashed Global Terror (Regnery, 2003),
./911report/chapter-3.txt:            President Bill Clinton ordered his National Security Council to coordinate the
./911report/chapter-3.txt:            President Bill Clinton's counterterrorism Presidential Decision Directives in 1995
./911report/chapter-6.txt:                Tanzania, President Bill Clinton and his chief aides explored ways of getting Bin
./911report/chapter-11.txt:            Whatever the weaknesses in the CIA's portraiture, both Presidents Bill Clinton and
```
```grep -r "Bill Clinton"``` recursively finds all the lines in the files in the directory and subdirectories containing the string "Bill Clinton". This is useful as we can tell from so many files in different subdirectories all talking about Bill Clinton. The lines of information also give hint on how the file content connects Bill Clinton to the text. 
### 2
```
(base) conggexu@Congges-MacBook-Pro technical % grep -ir "anGioplASTy"
./biomed/1468-6708-3-10.txt:        or CABG, percutaneous transluminal coronary angioplasty or
./biomed/1468-6708-3-10.txt:        stroke, CABG, angioplasty, other atherosclerotic
./biomed/1472-6963-3-7.txt:          angioplasty (PTCA) readmissions in diabetic patients who
./biomed/1472-6963-3-7.txt:        angioplasty
./biomed/cc350.txt:        percutaneous transluminal angioplasty [ 13] in patients
./biomed/cvm-2-6-278.txt:          following angioplasty [ 20]. While this phase I safety
./biomed/cvm-2-6-286.txt:        Carotid angioplasty and stenting is associated with a
./biomed/cvm-2-6-286.txt:        tip (Fig. 1). The wire serves as both the angioplasty
./biomed/cvm-2-6-286.txt:        The Saphenous Vein Graft Angioplasty Free of Emboli
./biomed/cvm-2-6-286.txt:        Vein Graft Angioplasty Free of Emboli, Randomized (SAFER)
./biomed/cvm-2-6-286.txt:        angioplasty and stenting using the PercuSurge GuardWire
./biomed/cvm-2-6-286.txt:          angioplasty guidewire with a filter that expands to 6 mm
./biomed/cvm-2-6-286.txt:          The Study of Angioplasty with Protection in Patients
./biomed/cvm-2-6-286.txt:          inch angioplasty wire with pore holes of 80 microns that
./biomed/cvm-2-6-286.txt:          retracted into any standard angioplasty balloon. A
./biomed/cvm-2-6-286.txt:          vascular intervention (angioplasty, stenting, etc.) the
./biomed/cvm-2-6-286.txt:        = Saphenous Vein Graft Angioplasty Free of Emboli study;
./biomed/cvm-2-6-286.txt:        SAFER = Saphenous Vein Graft Angioplasty Free of Emboli,
./biomed/cvm-2-6-286.txt:        Randomized trial; SAPPHIRE = The Study of Angioplasty with
./biomed/1468-6708-3-3.txt:        percutaneous transluminal coronary angioplasty (PTCA) or
./biomed/1468-6708-3-3.txt:        angioplasty; CABG = coronary artery bypass graft; ECG =
```
```grep -ir "anGioplASTy"``` recursively finds all the lines in the files in the directory and subdirectories containing the string "anGioplASTy" and this is case insensitive to the string. This is useful as it is case-insensitive to the string input. When we want to find something by using this key string, sometimes the string could be capitalized at the beginning of a sentence. If we use  -ir, we will not miss any information related to angioplasty.

```
(base) conggexu@Congges-MacBook-Pro technical % grep -ir "Hypertension" plos/
plos//pmed.0020104.txt:        hypertension [1]. They looked at how these CVD risk indicators are predicted by three broad
plos//pmed.0020104.txt:        practices in our growing cities. Screening for hypertension, hypercholesterolemia, and
plos//pmed.0010013.txt:        medication for generally healthy young adults with essential hypertension than a surgical
plos//pmed.0020113.txt:        Hypertension is common in affluent societies and a major risk factor for heart disease.
plos//pmed.0020113.txt:        In Canada, hypertension is the leading primary diagnosis for patient visits to physicians'
plos//pmed.0020113.txt:        hypertension drug use. During the period from 1993 to 2000, over 82,000 seniors were
plos//pmed.0020113.txt:        identified as new users of hypertension drugs. Less than a third of these patients received
plos//pmed.0020113.txt:        better at treating hypertension than much cheaper alternatives. Drug prices changed over
plos//pmed.0010058.txt:        treatment of other associated conditions such as hypertension and hyperlipidemia have
plos//pmed.0010058.txt:        anemia, weight loss, hypertension, hyperlipidemia, diarrhea, and fatigue [15]. Perhaps of
plos//pmed.0020160.txt:          and clinical exam and were also dichotomized for analysis. Hypertension was indicated by
plos//pmed.0010061.txt:        public health. For example, diabetes, visceral obesity, hypertension, and hyperinsulinemia
plos//pmed.0010062.txt:        confounding factors such as medications, hypertension, AHI, and factors listed above were
plos//pmed.0020162.txt:        17% decrease in hypertension, a 6% reduction in coronary heart disease, and a 15% reduction
plos//pmed.0020033.txt:        recently described for pulmonary arterial hypertension [18].
plos//pmed.0010052.txt:        disease and pulmonary hypertension after taking Fen-Phen [18]. A 2002 National Institutes
plos//pmed.0010068.txt:        connections between sleep apnea and hypertension, and between menopause and
plos//pmed.0020181.txt:        factors as co-variates. Weight loss improves hypertension and diabetes, so including these
plos//pmed.0020181.txt:        hypertension appeared to have little impact.
plos//pmed.0020045.txt:          444 μM/l), heavy proteinuria (3+ by dipstick or 3–6 gr/d), and hypertension. All patients
plos//pmed.0020045.txt:          μM/l), heavy proteinuria (3+ by dipstick), and hypertension. The diagnosis of FSGS was
plos//pmed.0020045.txt:        function, and hypertension were characterized by TED, IF, and increased tubular epithelial
plos//pmed.0020090.txt:        of uric acid are associated with hypertension and being overweight (other risk factors for
plos//pmed.0020123.txt:            cigarette smoking, or a physician-reported diagnosis of hypertension. Unfortunately,
plos//pmed.0020040.txt:        father has hypertension. He has had a 15-pound (lb) weight gain over the last year and has
plos//pmed.0020040.txt:        patients. Mild hypertension is often the only presenting sign of metabolic syndrome and
plos//pmed.0020040.txt:        hypertension [19,20].
plos//pmed.0020068.txt:        [2], hypertension [3], diabetes [4], ischemic heart disease, and all causes of mortality
plos//pmed.0020068.txt:        habitual activity that serves best to reduce risk for obesity, diabetes, hypertension, and
plos//pmed.0020068.txt:        skeletal muscles, and in turn improves fitness and reduces risk for diabetes, hypertension,
```
```grep -ir "Hypertension" plos/```recursively finds all the lines in the files in the specified directory ```plos/``` that contains the string "Hypertension" and this is case insensitive to the string. This is useful as it is case-insensitive to the string input and it can go to find the string with specified directory so we can filter information to obtain what we want. When we want to find something by using this key string, sometimes the string could be capitalized at the beginning of a sentence. If we use -ir, we will not miss any information related to alpha-1.

### 3
```
(base) conggexu@Congges-MacBook-Pro technical % grep -A 2 'globalisation' plos/journal.pbio.0020010.txt
        knowledge is essential in ‘selling’ their services to authors. The globalisation of
        publishing has combined with the globalisation of the networks and with the globalisation
        of research to provide opportunities for high-quality research conducted outside North
        America and Western Europe to be published in peer-reviewed open-access journals more
```

```The grep -A 2 'globalisation' plos/journal.pbio.0020010.txt``` command searches for the word 'globalisation' in the file named plos/journal.pbio.0020010.txt and displays the lines containing the matched word along with two lines of context following each match. By displaying lines that come after each match (in this case, two lines after), the command provides additional context around the occurrences of the word 'globalisation.' This can help users understand how the word is used in different contexts within the file.


```
(base) conggexu@Congges-MacBook-Pro technical % grep -A 5 "liberalization" government/Post_Rate_Comm/Cohenetal_comparison.txt
thus, creating cream-skimming opportunities under liberalization.
The burden that the restrictive USO imposes on a post is the
increase in its unit costs resulting from cream skimming under
liberalization caused by the requirements of uniform pricing and
levels of service. We use the term "burden of the USO" to
distinguish our concept from other papers that use the term "cost
of the USO."
We believe that insights into the burden of the USO can be
gained by comparing postal systems. Assuming that the keenest
--
aspect of the USO mitigating against liberalization. This paper
will be restricted to dealing with this aspect.
7
Motorcycles are the primary means of carrier transport in Italy
and automobiles are the primary means in the U.S.
8
--
liberalization, the probability seems slight until per capita
volumes are in the 100 to 150-piece range. Below that point the
possibility of a death spiral increases rapidly. Thus, we conclude
that the burden of the USO is much greater for low per capita
volume posts than for medium to high volume ones.
In order to make the model more useful for comparing Poste
```
```grep -A 5 "liberalization" government/Post_Rate_Comm/Cohenetal_comparison.txt``` searches for the word "liberalization" in the file Cohenetal_comparison.txt located within the government/Post_Rate_Comm directory. It also displays five lines of context following each match. It allows for a more efficient review of the document with specific instances of "liberalization". When conducting research or analysis related to "liberalization" in the context of government and policy, this command can help us find useful information efficiently.

### 4
```
(base) conggexu@Congges-MacBook-Pro technical % grep -m 5 "Annan" plos/journal.pbio.0020001.txt 
        Kofi Annan, the Secretary-General of the United Nations, recently called attention to
        the world scientific community closer to each other (Annan 2003). Mr. Annan stressed the
        development itself.” Indeed, Mr. Annan's sentiments have also been echoed recently by
        developing worlds actually remaining unchanged or even increasing, as Mr. Annan has
        Annan. There are many compelling reasons for the push to increase scientific input from the
```
```grep -m 5 "Annan" plos/journal.pbio.0020001.txt ``` searches for the word "Annan" in the file plos/journal.pbio.0020001.txt. It stops searching after finding five instances of "Annan" and prints out the first five lines with "Annan". When dealing with large text files, ```grep -m``` limits the search to a specific number of matches, making the search process more efficient. This can save time and system resources. It controls the lines displayed, helping avoid too much information.

```
(base) conggexu@Congges-MacBook-Pro technical % grep -m 3 "JSTOR" plos/journal.pbio.0020010.txt
        JSTOR is successful for reasons its founders did not intend. Bill Bowen's inspired
        electronic format. Few libraries have discarded the volumes digitised in JSTOR, but many
        important journal runs JSTOR has digitised. Paper holdings have not decreased dramatically,
```
```grep -m 3 "JSTOR" plos/journal.pbio.0020010.txt``` searches for "JSTOR" in the file plos/journal.pbio.0020010.txt. It stops searching after finding the third instances of "JSTOR" and prints out the first three lines with "JSTOR" instances. As there are many "JSTOR" in the specified file, a few "JSTOR" related instances are sufficient to tell us how "JSTOR" connects to the content.

### Citing ChatGPT
```
prompt: grep -m
ChatGPT:
The grep command in Unix and Unix-like operating systems is used to search for patterns in text files. The -m option is used to specify a maximum count of matches to be found before grep stops searching. It limits the number of lines that grep will output, and once it reaches the specified count, it will stop searching. This can be useful when you only want to see the first few occurrences of a pattern in a large file.

Here's the basic syntax for using the -m option with grep:

bash
Copy code
grep -m <count> <pattern> <file>
<count> is the maximum number of matches you want to find.
<pattern> is the regular expression or text pattern you want to search for.
<file> is the file in which you want to search for the pattern.
For example, if you want to find the first 5 occurrences of the word "apple" in a file called "fruits.txt," you can use the following command:

bash
Copy code
grep -m 5 "apple" fruits.txt
This will stop searching and display the output once it finds 5 occurrences of the word "apple" in the "fruits.txt" file.
```

I used the same syntax on the .technical with ```grep -m 5 "Annan" plos/journal.pbio.0020001.txt``` and the result matches the description of ChatGPT. Then I added my own understanding and explanation to the code. 



