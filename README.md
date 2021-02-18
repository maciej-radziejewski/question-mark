# QuestionMark

QuestionMark is an efficient way to prepare questions for online quizzes. At presents it consists of two parts:

- a text file format, inspired by MarkDown, for writing down the questions, and
- a Python script to convert the questions to a Moodle XML file that you can import to an instance of the Moodle learning management system, cf. https://moodle.org.

If you teach at a school or university that provides (a recent version of) Moodle to its students, and you have (a recent version of) Python 3 installed, you can immediately use QuestionMark.

The main idea behind this project is to make question preparation easier by allowing the author to focus on the contents of the questions, and not on the technical aspects of Moodle. The specific goals of QuestionMark are:

- make the question text look as natural and readable as possible,
- minimize the effort in writing and editing the questions,
- support multiple question types,
- support multiple sub-questions in one question,
- support question categories,
- support TeX equations.

## Why would you need QuestionMark?

An online quiz typically requires the teacher to trust the students' honesty. This is not a bad thing, but one should not put such honesty to too great a trial by handing similar sets of questions to multiple students. This makes it necessary to prepare multiple questions or variants of each question. My experience suggests that you need **15-30 questions for a short 15-minute quizz**, and **100+ questions/variants** for a longer quizz of 1 hour or more. Moodle does make it possible to create banks of questions, divided to categories. In a typical quizz each question would be chosen at random from a specified category, independently for each student. Several problems arise when preparing such a quizz.

1. Creating questions using the graphical interface takes a long time.

Of course, it may be different for you. For me it is much quicker to type something in a text editor than to click here and there to create an object, then to fill in this field, click there, select a score from a drop-down box etc. If I change my mind about a small detail concerning, say, 10 questions, it is faster to make such a change in a text file than edit each question in the web editor.

2. Some of Moodle's built-in question types do not support using mathematical formulas in answers (i.e. the options that the student would choose from).

You can use mathematics in question text and in the answers to multiple-choice questions, through a script called MathJax that parses the web page being displayed. However, the HTML specification prevents such rich content in the items displaed in a drop-down box, for example.

3. Some topics require rather complex questions with multiple sub-questions in order to make the test meaningful.

Splitting a question to several questions will not do if they are to be chosen at random. You could use the (very nice) "drag and drop" or "matching" question types, but these do not support equations in answers. Moreover, if the student gets, say, half of the answers right by chance, they will get 50% points.

4. The "embedded" aka "Cloze" question type is rather flexible and solves problem no. 3, but it requires the teacher to encode questions in a very technical way. The encoded questions are not easy to read and edit.

There exist formats such as Aiken (https://docs.moodle.org/310/en/Aiken_format) and GIFT (https://docs.moodle.org/310/en/GIFT_format) that aim to remedy some of the above problems, but not all of them. Aiken is very simple, but, at the time of this writing, it seems to be limited to multiple-choice and True/False questions. GIFT, though more versatile, is still somewhat technical. 

## What will your questions look like if you use QuestionMark?

Here is a sample.

	(in preparation)

## What do you do with the questions?

This repository will provide a Python script to convert your questions to Moodle's XML format. You can import the XML file to Moodle's question bank. Then you need to create a quizz in Moodle that uses the questions from the bank. More details will be available in the manual.
