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

#### 1. Creating questions using the graphical interface takes a long time.

Of course, it may be different for you. For me it is much quicker to type something in a text editor than to click here and there and fill in separate fields. If I change my mind about a small detail and want to change, say, 10 questions, it is faster to do it in a single text file than open each question in the web editor.

#### 2. Using mathematical formulas in question answers is limited.

Moodle does allow the use of mathematics through a script called MathJax that parses the web page being displayed. However, this is limited (because the HTML specification) to question text and the answers next to checkboxes and radio buttons. You cannot have formulas in a drop-down box, for example. So, if you want to use a drop-down box, you have to pay attention if one of the options might contain a formula.

#### 3. Some topics require rather complex questions with multiple sub-questions.

To check if a student understands a complex concept, you need to ask complex questions. Giving just one detail for the student to fill in is like leaving out just one piece of the puzzle: it makes your question prone to guesswork. So, essentially, you have the choice between the "Essay" question type, which needs manual grading (the students upload their answers or type freely), or the Cloze question type with multiple sub-questions. Yes, Moodle does have the (very nice) "drag and drop" and "matching" question types, but these do not support equations in answers. Moreover, with the default grading, if the student gets half of the answers right by chance, they will get 50% points.

#### 4. The "embedded" aka "Cloze" question type is rather flexible and solves problem no. 3, but it requires the teacher to encode questions in a very technical way. The encoded questions are not easy to read and edit.

There exist formats such as Aiken (https://docs.moodle.org/310/en/Aiken_format) and GIFT (https://docs.moodle.org/310/en/GIFT_format) that aim to remedy some of the above problems, but not all of them. Aiken is very simple, but, at the time of this writing, it seems to be limited to multiple-choice and True/False questions. GIFT, though more versatile, is still somewhat technical. 

## What will your questions look like if you use QuestionMark?

Here is a sample.

	(in preparation)

## What do you do with the questions?

This repository will provide a Python script to convert your questions to Moodle's XML format. You can import the XML file to Moodle's question bank. Then you need to create a quizz in Moodle that uses the questions from the bank. More details will be available in the manual.
