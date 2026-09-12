# study-smart-ai
an applicaton in which students can get get resources, study resources, smart planning, doubt support, and quizzes. 
"""
==========================================================
                    STUDYSMART AI
          Smart School Assistant - Python Project
             HACK-AI-THON 2026 | GRADES 7-9
==========================================================

FEATURES
--------
1. Find Study Resources
2. Practice Quiz
3. Ask a Doubt
4. Smart Recommendation
5. Personalized Study Plan
6. Exit

QUIZ DATABASE
-------------
7 subjects
25 unique questions per subject
175 unique questions total

Quiz lengths:
5, 10, 15 or 25 questions

Questions NEVER repeat inside one quiz.
Correct answers are distributed across A, B, C and D.

This is a rule-based Python prototype.
==========================================================
"""

import random
import tkinter as tk
from tkinter import messagebox, ttk


# ==========================================================
# STEP 1 - STUDY RESOURCES
# ==========================================================

RESOURCES = {

    "Science": {
        "Photosynthesis": [
            "Easy explanation",
            "Key points",
            "Practice quiz",
            "Revision tips"
        ],
        "Force": [
            "Easy explanation",
            "Important definitions",
            "Solved examples",
            "Practice questions"
        ]
    },

    "Maths": {
        "Fractions": [
            "Fraction basics",
            "Worked examples",
            "Practice questions",
            "Quick quiz"
        ],
        "Quadrilaterals": [
            "Types of quadrilaterals",
            "Important properties",
            "Solved examples",
            "Practice questions"
        ]
    },

    "English": {
        "Grammar": [
            "Grammar rules",
            "Examples",
            "Exercises",
            "Practice quiz"
        ],
        "Tenses": [
            "Types of tenses",
            "Examples",
            "Practice exercises",
            "Quick revision"
        ]
    },

    "History": {
        "Marathas": [
            "Rise of the Marathas",
            "Important events",
            "Key personalities",
            "Revision questions"
        ],
        "Revolt": [
            "Important events",
            "Causes",
            "Major personalities",
            "Practice questions"
        ]
    },

    "Geography": {
        "Resources": [
            "Types of resources",
            "Important definitions",
            "Examples",
            "Practice questions"
        ],
        "Agriculture": [
            "Types of resources",
            "Major crops",
            "Important terms",
            "Revision questions"
        ]
    },

    "Computer": {
        "Python": [
            "Python basics",
            "If-else examples",
            "Loops",
            "Practice programs"
        ],
        "Algorithms": [
            "What is an algorithm?",
            "Step-by-step examples",
            "Flowchart basics",
            "Practice problems"
        ]
    },

    "Politics": {
        "Constitution": [
            "Basic constitutional ideas",
            "Fundamental rights",
            "Important terms",
            "Quick revision"
        ],
        "Elections": [
            "Voting and elections",
            "Universal adult franchise",
            "Election Commission",
            "Practice questions"
        ]
    }
}


# ==========================================================
# STEP 2 - 175 UNIQUE QUIZ QUESTIONS
# ==========================================================

QUIZ = {

# ==========================================================
# SCIENCE - 25 QUESTIONS
# ==========================================================

"Science": [

{
"question": "What do green plants use to make food?",
"options": ["A. Sunlight", "B. Rocks", "C. Plastic", "D. Metal"],
"answer": "A"
},

{
"question": "Which gas is used during photosynthesis?",
"options": ["A. Oxygen", "B. Carbon dioxide", "C. Helium", "D. Hydrogen"],
"answer": "B"
},

{
"question": "Which part of a plant mainly carries out photosynthesis?",
"options": ["A. Root", "B. Stem", "C. Leaf", "D. Flower"],
"answer": "C"
},

{
"question": "A push or pull is called:",
"options": ["A. Energy", "B. Force", "C. Speed", "D. Mass"],
"answer": "B"
},

{
"question": "Which force pulls objects towards Earth?",
"options": ["A. Magnetic force", "B. Friction", "C. Gravity", "D. Muscular force"],
"answer": "C"
},

{
"question": "Which substance is necessary for photosynthesis besides carbon dioxide?",
"options": ["A. Water", "B. Plastic", "C. Sand", "D. Iron"],
"answer": "A"
},

{
"question": "The green pigment in leaves is called:",
"options": ["A. Haemoglobin", "B. Chlorophyll", "C. Keratin", "D. Melanin"],
"answer": "B"
},

{
"question": "Which organelle contains chlorophyll?",
"options": ["A. Nucleus", "B. Ribosome", "C. Chloroplast", "D. Vacuole"],
"answer": "C"
},

{
"question": "What is produced as a by-product of photosynthesis?",
"options": ["A. Nitrogen", "B. Oxygen", "C. Helium", "D. Hydrogen"],
"answer": "B"
},

{
"question": "Which force opposes motion between surfaces?",
"options": ["A. Gravity", "B. Friction", "C. Magnetic force", "D. Buoyant force"],
"answer": "B"
},

{
"question": "Which force can act without physical contact?",
"options": ["A. Muscular force", "B. Friction", "C. Gravitational force", "D. Push"],
"answer": "C"
},

{
"question": "A force can change the ______ of an object.",
"options": ["A. Shape", "B. Name", "C. Colour only", "D. Material only"],
"answer": "A"
},

{
"question": "Which of these is a contact force?",
"options": ["A. Gravity", "B. Magnetic force", "C. Muscular force", "D. Electrostatic force"],
"answer": "C"
},

{
"question": "Which instrument is commonly used to measure force?",
"options": ["A. Thermometer", "B. Spring balance", "C. Barometer", "D. Stopwatch"],
"answer": "B"
},

{
"question": "The SI unit of force is:",
"options": ["A. Joule", "B. Watt", "C. Newton", "D. Pascal"],
"answer": "C"
},

{
"question": "Why are handles of some tools made rough?",
"options": ["A. To reduce friction", "B. To increase friction", "C. To remove gravity", "D. To increase mass"],
"answer": "B"
},

{
"question": "Which force helps us write with a pencil?",
"options": ["A. Friction", "B. Gravity", "C. Magnetic force", "D. Buoyant force"],
"answer": "A"
},

{
"question": "What happens when equal forces act in opposite directions?",
"options": ["A. They always increase motion", "B. They cancel each other", "C. They create light", "D. They create heat only"],
"answer": "B"
},

{
"question": "Plants take in carbon dioxide mainly through:",
"options": ["A. Roots", "B. Flowers", "C. Stomata", "D. Seeds"],
"answer": "C"
},

{
"question": "The food produced during photosynthesis is mainly:",
"options": ["A. Glucose", "B. Protein", "C. Salt", "D. Fat"],
"answer": "A"
},

{
"question": "Which factor provides energy for photosynthesis?",
"options": ["A. Moonlight", "B. Sunlight", "C. Sound", "D. Wind"],
"answer": "B"
},

{
"question": "Friction is useful because it helps us:",
"options": ["A. Walk", "B. Float in air", "C. Become weightless", "D. Stop gravity"],
"answer": "A"
},

{
"question": "Which force is responsible for objects falling down?",
"options": ["A. Friction", "B. Gravity", "C. Muscular force", "D. Magnetic force"],
"answer": "B"
},

{
"question": "A force can change the speed of an object.",
"options": ["A. True", "B. False", "C. Only in water", "D. Only in space"],
"answer": "A"
},

{
"question": "Which part of the plant absorbs water from soil?",
"options": ["A. Leaf", "B. Root", "C. Flower", "D. Fruit"],
"answer": "B"
}

],


# ==========================================================
# MATHS - 25 QUESTIONS
# ==========================================================

"Maths": [

{
"question": "What is 1/2 + 1/4?",
"options": ["A. 1/4", "B. 2/4", "C. 3/4", "D. 4/4"],
"answer": "C"
},

{
"question": "Which fraction is larger?",
"options": ["A. 1/2", "B. 1/8", "C. 1/10", "D. 1/20"],
"answer": "A"
},

{
"question": "What is 3/4 of 20?",
"options": ["A. 10", "B. 12", "C. 15", "D. 18"],
"answer": "C"
},

{
"question": "How many sides does a quadrilateral have?",
"options": ["A. 3", "B. 4", "C. 5", "D. 6"],
"answer": "B"
},

{
"question": "A square has how many equal sides?",
"options": ["A. 2", "B. 3", "C. 4", "D. 5"],
"answer": "C"
},

{
"question": "What is 2/3 + 1/3?",
"options": ["A. 1", "B. 2/3", "C. 1/3", "D. 4/3"],
"answer": "A"
},

{
"question": "What is 5/6 - 1/6?",
"options": ["A. 1/6", "B. 2/3", "C. 5/6", "D. 1/2"],
"answer": "B"
},

{
"question": "Which fraction is equivalent to 1/2?",
"options": ["A. 2/3", "B. 3/6", "C. 4/10", "D. 5/12"],
"answer": "B"
},

{
"question": "What is 2/5 × 10?",
"options": ["A. 2", "B. 4", "C. 5", "D. 8"],
"answer": "B"
},

{
"question": "The sum of angles of a quadrilateral is:",
"options": ["A. 180°", "B. 270°", "C. 360°", "D. 90°"],
"answer": "C"
},

{
"question": "Opposite sides of a parallelogram are:",
"options": ["A. Equal and parallel", "B. Unequal", "C. Always perpendicular", "D. Curved"],
"answer": "A"
},

{
"question": "A rectangle has how many right angles?",
"options": ["A. 1", "B. 2", "C. 3", "D. 4"],
"answer": "D"
},

{
"question": "A rhombus has:",
"options": ["A. Four equal sides", "B. No equal sides", "C. Three sides", "D. Five sides"],
"answer": "A"
},

{
"question": "A square is also a:",
"options": ["A. Triangle", "B. Parallelogram", "C. Pentagon", "D. Circle"],
"answer": "B"
},

{
"question": "What is 3/5 + 1/5?",
"options": ["A. 2/5", "B. 4/5", "C. 3/10", "D. 1"],
"answer": "B"
},

{
"question": "What is 7/8 - 3/8?",
"options": ["A. 1/2", "B. 3/8", "C. 5/8", "D. 7/8"],
"answer": "A"
},

{
"question": "Which number is the numerator in 7/9?",
"options": ["A. 7", "B. 9", "C. 16", "D. 2"],
"answer": "A"
},

{
"question": "Which number is the denominator in 5/8?",
"options": ["A. 5", "B. 8", "C. 13", "D. 3"],
"answer": "B"
},

{
"question": "A trapezium has at least:",
"options": ["A. One pair of parallel sides", "B. Four equal sides", "C. No sides", "D. Three pairs of parallel sides"],
"answer": "A"
},

{
"question": "The diagonals of a rectangle are:",
"options": ["A. Unequal", "B. Equal", "C. Always perpendicular", "D. Curved"],
"answer": "B"
},

{
"question": "What is 1/3 of 12?",
"options": ["A. 2", "B. 3", "C. 4", "D. 6"],
"answer": "C"
},

{
"question": "What is 25% of 100?",
"options": ["A. 10", "B. 20", "C. 25", "D. 50"],
"answer": "C"
},

{
"question": "What is 3 × 4 + 2?",
"options": ["A. 14", "B. 18", "C. 20", "D. 12"],
"answer": "A"
},

{
"question": "A polygon with five sides is called:",
"options": ["A. Hexagon", "B. Pentagon", "C. Quadrilateral", "D. Triangle"],
"answer": "B"
},

{
"question": "How many diagonals does a quadrilateral have?",
"options": ["A. 1", "B. 2", "C. 3", "D. 4"],
"answer": "B"
}

],


# ==========================================================
# ENGLISH - 25 QUESTIONS
# ==========================================================

"English": [

{
"question": "Choose the correct sentence.",
"options": ["A. She go to school.", "B. She goes to school.", "C. She going school.", "D. She gone school."],
"answer": "B"
},

{
"question": "Which word is a verb in 'The boy runs fast'?",
"options": ["A. Boy", "B. The", "C. Runs", "D. Fast"],
"answer": "C"
},

{
"question": "What is the plural of 'child'?",
"options": ["A. Childs", "B. Childes", "C. Children", "D. Childrens"],
"answer": "C"
},

{
"question": "Which word is a noun?",
"options": ["A. Beautiful", "B. Run", "C. School", "D. Quickly"],
"answer": "C"
},

{
"question": "Which sentence is in the past tense?",
"options": ["A. I play cricket.", "B. I am playing cricket.", "C. I played cricket.", "D. I will play cricket."],
"answer": "C"
},

{
"question": "Which word is an adjective?",
"options": ["A. Beautiful", "B. Quickly", "C. Run", "D. School"],
"answer": "A"
},

{
"question": "Choose the correct article: 'I saw ___ elephant.'",
"options": ["A. a", "B. an", "C. the", "D. no"],
"answer": "B"
},

{
"question": "Which pronoun can replace 'Riya'?",
"options": ["A. He", "B. It", "C. She", "D. They"],
"answer": "C"
},

{
"question": "What is the opposite of 'ancient'?",
"options": ["A. Old", "B. Modern", "C. Historic", "D. Early"],
"answer": "B"
},

{
"question": "Which word is an adverb?",
"options": ["A. Slowly", "B. Beautiful", "C. School", "D. Jump"],
"answer": "A"
},

{
"question": "Choose the correct form: 'They ___ playing.'",
"options": ["A. is", "B. am", "C. are", "D. was"],
"answer": "C"
},

{
"question": "Which punctuation mark ends a question?",
"options": ["A. Full stop", "B. Comma", "C. Question mark", "D. Colon"],
"answer": "C"
},

{
"question": "What is the past tense of 'go'?",
"options": ["A. Goed", "B. Went", "C. Gone", "D. Going"],
"answer": "B"
},

{
"question": "What is the opposite of 'difficult'?",
"options": ["A. Hard", "B. Easy", "C. Tough", "D. Complex"],
"answer": "B"
},

{
"question": "Which is a synonym of 'happy'?",
"options": ["A. Sad", "B. Angry", "C. Joyful", "D. Tired"],
"answer": "C"
},

{
"question": "Which sentence is in the future tense?",
"options": ["A. I played.", "B. I play.", "C. I am playing.", "D. I will play."],
"answer": "D"
},

{
"question": "Which word is a conjunction?",
"options": ["A. And", "B. Beautiful", "C. Quickly", "D. School"],
"answer": "A"
},

{
"question": "Choose the correct sentence.",
"options": ["A. He have a book.", "B. He has a book.", "C. He having book.", "D. He haves book."],
"answer": "B"
},

{
"question": "What is the plural of 'mouse'?",
"options": ["A. Mouses", "B. Mouse", "C. Mice", "D. Mices"],
"answer": "C"
},

{
"question": "Which word is a preposition?",
"options": ["A. Under", "B. Quickly", "C. Beautiful", "D. Sing"],
"answer": "A"
},

{
"question": "Identify the noun: 'The teacher entered the classroom.'",
"options": ["A. Entered", "B. The", "C. Teacher", "D. The"],
"answer": "C"
},

{
"question": "Which sentence is grammatically correct?",
"options": ["A. We was happy.", "B. We were happy.", "C. We is happy.", "D. We be happy."],
"answer": "B"
},

{
"question": "What is the comparative form of 'tall'?",
"options": ["A. Tallest", "B. More tall", "C. Taller", "D. Talling"],
"answer": "C"
},

{
"question": "Which word is an interjection?",
"options": ["A. Wow!", "B. School", "C. Running", "D. Quickly"],
"answer": "A"
},

{
"question": "Choose the correct spelling.",
"options": ["A. Becaus", "B. Because", "C. Becouse", "D. Becase"],
"answer": "B"
}

],


# ==========================================================
# HISTORY - 25 QUESTIONS
# ==========================================================

"History": [

{
"question": "Who was Chhatrapati Shivaji?",
"options": ["A. A Maratha ruler", "B. A scientist", "C. A poet", "D. A mathematician"],
"answer": "A"
},

{
"question": "Who was the mother of Shivaji?",
"options": ["A. Jijabai", "B. Razia", "C. Nur Jahan", "D. Rani Lakshmibai"],
"answer": "A"
},

{
"question": "Who was an important Bhakti saint of Maharashtra?",
"options": ["A. Tukaram", "B. Newton", "C. Akbar", "D. Columbus"],
"answer": "A"
},

{
"question": "The Maratha power grew strongly under:",
"options": ["A. Shivaji", "B. Ashoka", "C. Harsha", "D. Chandragupta"],
"answer": "A"
},

{
"question": "The Anglo-Maratha conflicts involved the:",
"options": ["A. British and Marathas", "B. French and Romans", "C. Greeks and Persians", "D. Cholas and Pandyas"],
"answer": "A"
},

{
"question": "Shivaji was born in:",
"options": ["A. 1630", "B. 1707", "C. 1757", "D. 1857"],
"answer": "A"
},

{
"question": "Shivaji's father was:",
"options": ["A. Shahaji", "B. Akbar", "C. Aurangzeb", "D. Baji Rao"],
"answer": "A"
},

{
"question": "Which saint was associated with the Bhakti movement in Maharashtra?",
"options": ["A. Dnyaneshwar", "B. Newton", "C. Vasco da Gama", "D. Babur"],
"answer": "A"
},

{
"question": "Which saint was known for devotional poetry in Maharashtra?",
"options": ["A. Namdev", "B. Einstein", "C. Clive", "D. Babar"],
"answer": "A"
},

{
"question": "Who was Ramdas?",
"options": ["A. A Bhakti saint", "B. A British officer", "C. A scientist", "D. A Mughal emperor"],
"answer": "A"
},

{
"question": "Who succeeded Shivaji as ruler of the Maratha kingdom?",
"options": ["A. Sambhaji", "B. Ashoka", "C. Akbar", "D. Humayun"],
"answer": "A"
},

{
"question": "Aurangzeb was a ruler of the:",
"options": ["A. Mughal Empire", "B. Maratha Empire", "C. Chola Empire", "D. Mauryan Empire"],
"answer": "A"
},

{
"question": "The Maratha navy was strongly associated with:",
"options": ["A. Kanhoji Angre", "B. Shivaji's teacher", "C. Akbar", "D. Robert Clive"],
"answer": "A"
},

{
"question": "The Maratha administration was headed by the:",
"options": ["A. Chhatrapati", "B. Governor-General", "C. Viceroy", "D. President"],
"answer": "A"
},

{
"question": "The Peshwa became an important position in:",
"options": ["A. Maratha administration", "B. Mughal art", "C. British Parliament", "D. Chola navy"],
"answer": "A"
},

{
"question": "The Third Anglo-Maratha War ended in:",
"options": ["A. 1818", "B. 1757", "C. 1857", "D. 1947"],
"answer": "A"
},

{
"question": "The First Anglo-Maratha War began in:",
"options": ["A. 1775", "B. 1818", "C. 1857", "D. 1942"],
"answer": "A"
},

{
"question": "Which event is associated with the year 1857?",
"options": ["A. Revolt of 1857", "B. First Anglo-Maratha War", "C. Battle of Plassey", "D. Quit India Movement"],
"answer": "A"
},

{
"question": "The Revolt of 1857 began mainly as a:",
"options": ["A. Revolt against British rule", "B. Trade agreement", "C. Religious festival", "D. Scientific movement"],
"answer": "A"
},

{
"question": "Mangal Pandey is associated with:",
"options": ["A. Revolt of 1857", "B. Maratha navy", "C. Bhakti movement", "D. Green Revolution"],
"answer": "A"
},

{
"question": "Rani Lakshmibai was the queen of:",
"options": ["A. Jhansi", "B. Delhi", "C. Pune", "D. Mysore"],
"answer": "A"
},

{
"question": "The British East India Company expanded its political power mainly through:",
"options": ["A. Wars and political policies", "B. Space travel", "C. Farming", "D. Scientific research"],
"answer": "A"
},

{
"question": "The Marathas were especially powerful in:",
"options": ["A. Western India", "B. Northern Europe", "C. South America", "D. Australia"],
"answer": "A"
},

{
"question": "Which fort was strongly associated with Shivaji?",
"options": ["A. Raigad", "B. Red Fort only", "C. Agra Fort only", "D. Golconda only"],
"answer": "A"
},

{
"question": "The Maratha Confederacy became powerful after:",
"options": ["A. The rise of Maratha leaders and the Peshwas", "B. The Industrial Revolution", "C. The French Revolution", "D. The Green Revolution"],
"answer": "A"
}

],


# ==========================================================
# GEOGRAPHY - 25 QUESTIONS
# ==========================================================

"Geography": [

{
"question": "Which is a natural resource?",
"options": ["A. Water", "B. Plastic bottle", "C. Computer", "D. Car"],
"answer": "A"
},

{
"question": "Which is a renewable resource?",
"options": ["A. Coal", "B. Petroleum", "C. Solar energy", "D. Natural gas"],
"answer": "C"
},

{
"question": "Agriculture mainly involves:",
"options": ["A. Growing crops", "B. Building computers", "C. Making cars", "D. Flying aircraft"],
"answer": "A"
},

{
"question": "Which is a major food crop?",
"options": ["A. Rice", "B. Iron", "C. Coal", "D. Gold"],
"answer": "A"
},

{
"question": "Resources that can naturally be replaced are called:",
"options": ["A. Renewable resources", "B. Artificial resources", "C. Permanent resources", "D. Manufactured resources"],
"answer": "A"
},

{
"question": "Which is a non-renewable resource?",
"options": ["A. Solar energy", "B. Wind", "C. Coal", "D. Sunlight"],
"answer": "C"
},

{
"question": "Which crop requires a warm and wet climate?",
"options": ["A. Rice", "B. Wheat", "C. Barley", "D. Gram"],
"answer": "A"
},

{
"question": "Which crop is commonly known as a cash crop?",
"options": ["A. Cotton", "B. Rice", "C. Wheat", "D. Maize"],
"answer": "A"
},

{
"question": "Which resource is essential for drinking and agriculture?",
"options": ["A. Water", "B. Iron", "C. Coal", "D. Gold"],
"answer": "A"
},

{
"question": "Which is an example of human-made resource?",
"options": ["A. Road", "B. River", "C. Forest", "D. Sunlight"],
"answer": "A"
},

{
"question": "Which soil is suitable for growing cotton?",
"options": ["A. Black soil", "B. Mountain soil only", "C. Desert sand", "D. Laterite only"],
"answer": "A"
},

{
"question": "Which crop is mainly grown in the rabi season?",
"options": ["A. Wheat", "B. Rice", "C. Cotton", "D. Jute"],
"answer": "A"
},

{
"question": "Which crop is commonly associated with the kharif season?",
"options": ["A. Rice", "B. Wheat", "C. Mustard", "D. Gram"],
"answer": "A"
},

{
"question": "What is irrigation?",
"options": ["A. Artificial supply of water to crops", "B. Cutting forests", "C. Mining coal", "D. Building roads"],
"answer": "A"
},

{
"question": "Which method saves water by delivering it near plant roots?",
"options": ["A. Drip irrigation", "B. Flooding", "C. Overwatering", "D. Rainfall only"],
"answer": "A"
},

{
"question": "Which is a mineral resource?",
"options": ["A. Iron ore", "B. Sunlight", "C. Wind", "D. Rain"],
"answer": "A"
},

{
"question": "Forests provide:",
"options": ["A. Timber and other useful products", "B. Only plastic", "C. Only metals", "D. Only machines"],
"answer": "A"
},

{
"question": "Which is a source of renewable energy?",
"options": ["A. Wind", "B. Coal", "C. Petroleum", "D. Natural gas"],
"answer": "A"
},

{
"question": "What is conservation?",
"options": ["A. Careful use and protection of resources", "B. Wasting resources", "C. Removing forests", "D. Polluting water"],
"answer": "A"
},

{
"question": "Which farming method involves growing crops and rearing animals together?",
"options": ["A. Mixed farming", "B. Plantation farming", "C. Shifting cultivation", "D. Terrace farming"],
"answer": "A"
},

{
"question": "Tea is commonly grown in:",
"options": ["A. Assam", "B. Rajasthan desert", "C. Punjab only", "D. Ladakh"],
"answer": "A"
},

{
"question": "Which crop is used to make sugar?",
"options": ["A. Sugarcane", "B. Wheat", "C. Cotton", "D. Tea"],
"answer": "A"
},

{
"question": "Which gas is a major greenhouse gas?",
"options": ["A. Carbon dioxide", "B. Oxygen", "C. Helium", "D. Neon"],
"answer": "A"
},

{
"question": "Which resource is obtained from underground deposits?",
"options": ["A. Minerals", "B. Sunlight", "C. Wind", "D. Rainfall"],
"answer": "A"
},

{
"question": "Why should natural resources be conserved?",
"options": ["A. To ensure availability for the future", "B. To waste them faster", "C. To increase pollution", "D. To destroy habitats"],
"answer": "A"
}

],


# ==========================================================
# COMPUTER - 25 QUESTIONS
# ==========================================================

"Computer": [

{
"question": "Which language are we using for this project?",
"options": ["A. Java", "B. Python", "C. HTML", "D. SQL"],
"answer": "B"
},

{
"question": "Which statement is used to make a decision in Python?",
"options": ["A. if", "B. print", "C. input", "D. import"],
"answer": "A"
},

{
"question": "Which function takes input from the user?",
"options": ["A. output()", "B. input()", "C. answer()", "D. readtext()"],
"answer": "B"
},

{
"question": "Which loop can repeat instructions?",
"options": ["A. for", "B. print", "C. input", "D. if"],
"answer": "A"
},

{
"question": "What does a variable store?",
"options": ["A. A value", "B. Only a picture", "C. Only a sound", "D. Nothing"],
"answer": "A"
},

{
"question": "Which function displays output in Python?",
"options": ["A. show()", "B. display()", "C. print()", "D. output()"],
"answer": "C"
},

{
"question": "Which symbol is used for multiplication in Python?",
"options": ["A. x", "B. *", "C. #", "D. %"],
"answer": "B"
},

{
"question": "Which symbol is used for division?",
"options": ["A. /", "B. // only", "C. :", "D. **"],
"answer": "A"
},

{
"question": "Which operator checks whether two values are equal?",
"options": ["A. =", "B. ==", "C. !=", "D. >"],
"answer": "B"
},

{
"question": "Which operator means 'not equal to'?",
"options": ["A. ==", "B. =", "C. !=", "D. <="],
"answer": "C"
},

{
"question": "What is the purpose of an algorithm?",
"options": ["A. To give step-by-step instructions", "B. To draw pictures only", "C. To store music", "D. To delete computers"],
"answer": "A"
},

{
"question": "A flowchart represents an algorithm using:",
"options": ["A. Symbols", "B. Songs", "C. Paragraphs only", "D. Photos only"],
"answer": "A"
},

{
"question": "Which Python data type stores whole numbers?",
"options": ["A. int", "B. str", "C. float", "D. bool"],
"answer": "A"
},

{
"question": "Which data type stores text?",
"options": ["A. int", "B. str", "C. float", "D. bool"],
"answer": "B"
},

{
"question": "Which value represents True or False?",
"options": ["A. Boolean", "B. String", "C. Integer", "D. Float"],
"answer": "A"
},

{
"question": "What does range(5) normally generate?",
"options": ["A. 1 to 5", "B. 0 to 4", "C. 5 to 10", "D. 0 to 5"],
"answer": "B"
},

{
"question": "Which keyword is used to define a function?",
"options": ["A. function", "B. define", "C. def", "D. fun"],
"answer": "C"
},

{
"question": "Which loop is useful when the number of repetitions is known?",
"options": ["A. for", "B. if", "C. else", "D. print"],
"answer": "A"
},

{
"question": "Which keyword runs when an if condition is false?",
"options": ["A. repeat", "B. else", "C. false", "D. stop"],
"answer": "B"
},

{
"question": "What does % give in Python?",
"options": ["A. Quotient", "B. Remainder", "C. Product", "D. Power"],
"answer": "B"
},

{
"question": "What is the result of 10 % 3?",
"options": ["A. 0", "B. 1", "C. 2", "D. 3"],
"answer": "B"
},

{
"question": "Which symbol starts a comment in Python?",
"options": ["A. //", "B. #", "C. /*", "D. --"],
"answer": "B"
},

{
"question": "What is debugging?",
"options": ["A. Finding and fixing errors", "B. Writing music", "C. Drawing a flowchart", "D. Printing documents"],
"answer": "A"
},

{
"question": "Which keyword is used to repeat a loop while a condition is true?",
"options": ["A. while", "B. repeat", "C. loop", "D. during"],
"answer": "A"
},

{
"question": "Which of these is a valid Python variable name?",
"options": ["A. 2name", "B. student_name", "C. student-name", "D. class"],
"answer": "B"
}

],


# ==========================================================
# POLITICS - 25 QUESTIONS
# ==========================================================

"Politics": [

{
"question": "What is the supreme law of India?",
"options": ["A. Constitution", "B. Newspaper", "C. Textbook", "D. Election poster"],
"answer": "A"
},

{
"question": "What is the minimum voting age in India?",
"options": ["A. 16", "B. 17", "C. 18", "D. 21"],
"answer": "C"
},

{
"question": "Which body conducts elections in India?",
"options": ["A. Election Commission of India", "B. Supreme Court", "C. Parliament Library", "D. Police Department"],
"answer": "A"
},

{
"question": "Universal adult franchise means:",
"options": ["A. Eligible adult citizens can vote", "B. Only rich people can vote", "C. Only students can vote", "D. Only government workers can vote"],
"answer": "A"
},

{
"question": "Which Article deals with elections to the Lok Sabha and State Assemblies?",
"options": ["A. Article 14", "B. Article 21", "C. Article 326", "D. Article 370"],
"answer": "C"
},

{
"question": "The Constitution of India came into force on:",
"options": ["A. 15 August 1947", "B. 26 January 1950", "C. 26 November 1949", "D. 2 October 1950"],
"answer": "B"
},

{
"question": "The Constitution was adopted on:",
"options": ["A. 26 November 1949", "B. 15 August 1947", "C. 26 January 1950", "D. 14 November 1948"],
"answer": "A"
},

{
"question": "India is described as a:",
"options": ["A. Democratic republic", "B. Absolute monarchy", "C. Military dictatorship", "D. Colonial state"],
"answer": "A"
},

{
"question": "Who is the constitutional head of India?",
"options": ["A. Prime Minister", "B. President", "C. Chief Justice", "D. Speaker"],
"answer": "B"
},

{
"question": "Who is the head of the Union Council of Ministers?",
"options": ["A. President", "B. Prime Minister", "C. Governor", "D. Chief Justice"],
"answer": "B"
},

{
"question": "The Indian Parliament consists of:",
"options": ["A. Lok Sabha and Rajya Sabha", "B. Only Lok Sabha", "C. Only Rajya Sabha", "D. Supreme Court and Lok Sabha"],
"answer": "A"
},

{
"question": "Which House is also called the House of the People?",
"options": ["A. Rajya Sabha", "B. Lok Sabha", "C. Vidhan Parishad", "D. Supreme Court"],
"answer": "B"
},

{
"question": "Which House is called the Council of States?",
"options": ["A. Lok Sabha", "B. Rajya Sabha", "C. Vidhan Sabha", "D. Gram Sabha"],
"answer": "B"
},

{
"question": "Members of Lok Sabha are generally elected directly by:",
"options": ["A. Voters", "B. Judges", "C. Governors", "D. Police officers"],
"answer": "A"
},

{
"question": "The Election Commission of India was established in:",
"options": ["A. 1947", "B. 1950", "C. 1952", "D. 1960"],
"answer": "B"
},

{
"question": "The first general elections in India were held in:",
"options": ["A. 1947-48", "B. 1951-52", "C. 1960-61", "D. 1971-72"],
"answer": "B"
},

{
"question": "A person who votes in an election is called a:",
"options": ["A. Voter", "B. Candidate", "C. Minister", "D. Judge"],
"answer": "A"
},

{
"question": "The right to vote is an important feature of:",
"options": ["A. Democracy", "B. Monarchy", "C. Dictatorship", "D. Colonial rule"],
"answer": "A"
},

{
"question": "Fundamental Rights are included in the:",
"options": ["A. Constitution", "B. Newspaper", "C. Election manifesto", "D. School timetable"],
"answer": "A"
},

{
"question": "Which body makes laws for the Union?",
"options": ["A. Parliament", "B. Police", "C. Election Commission", "D. Army"],
"answer": "A"
},

{
"question": "A constituency is:",
"options": ["A. An area represented by an elected member", "B. A court", "C. A school", "D. A government office"],
"answer": "A"
},

{
"question": "What is democracy?",
"options": ["A. Government by the people", "B. Government by one king", "C. Government by the army", "D. Government without citizens"],
"answer": "A"
},

{
"question": "Why are elections important?",
"options": ["A. They allow citizens to choose representatives", "B. They remove all laws", "C. They stop voting", "D. They appoint judges directly"],
"answer": "A"
},

{
"question": "Which principle means every eligible adult has an equal vote?",
"options": ["A. Universal adult franchise", "B. Hereditary rule", "C. Monarchy", "D. Colonialism"],
"answer": "A"
},

{
"question": "The Constitution protects the rights of:",
"options": ["A. Citizens", "B. Only ministers", "C. Only judges", "D. Only government employees"],
"answer": "A"
}

]
}


# ==========================================================
# STEP 3 - DOUBT ANSWERS
# ==========================================================

DOUBTS = {

    "Photosynthesis":
        "Photosynthesis is the process by which green plants make "
        "food using sunlight, water and carbon dioxide.",

    "Force":
        "Force is a push or pull that can change the motion, direction "
        "or shape of an object.",

    "Fractions":
        "A fraction represents a part of a whole. The top number is "
        "the numerator and the bottom number is the denominator.",

    "Quadrilaterals":
        "A quadrilateral is a polygon with four sides. Its interior "
        "angles add up to 360 degrees.",

    "Grammar":
        "Grammar is the set of rules used to form correct sentences.",

    "Tenses":
        "Tenses show the time of an action. The three basic tenses "
        "are past, present and future.",

    "Marathas":
        "The Marathas became a powerful political force in India, "
        "especially under Chhatrapati Shivaji.",

    "Revolt":
        "The Revolt of 1857 was a major uprising against British rule "
        "in India.",

    "Resources":
        "Resources are things that are useful to humans, such as "
        "water, forests, minerals and sunlight.",

    "Agriculture":
        "Agriculture is the practice of growing crops and rearing "
        "animals for human use.",

    "Python":
        "Python is a programming language known for simple and "
        "readable syntax.",

    "Algorithms":
        "An algorithm is a step-by-step procedure used to solve "
        "a problem or complete a task.",

    "Constitution":
        "The Constitution is the supreme law of India. It explains "
        "the structure of government and the rights of citizens.",

    "Elections":
        "Elections allow eligible citizens to choose their representatives "
        "through voting."
}


# ==========================================================
# STEP 4 - DISPLAY FUNCTIONS
# ==========================================================

def line():
    print("=" * 60)


def header(title):
    line()
    print(title)
    line()


# ==========================================================
# STEP 5 - WELCOME
# ==========================================================

def welcome():

    header("                 STUDYSMART AI")

    print("Welcome to your smart study assistant!")
    print("Let's make studying easier and more interactive.\n")

    name = input("What is your name? ").strip()

    if name == "":
        name = "Student"

    print("\nHello", name + "!")
    print("Ready to study smarter?\n")

    return name


# ==========================================================
# STEP 6 - SUBJECT MENU
# ==========================================================

def choose_subject():

    while True:

        print("\nChoose your subject:")

        print("1. Science")
        print("2. Maths")
        print("3. English")
        print("4. History")
        print("5. Geography")
        print("6. Computer")
        print("7. Politics / Civics")

        choice = input("\nEnter your choice (1-7): ").strip()

        subjects = {
            "1": "Science",
            "2": "Maths",
            "3": "English",
            "4": "History",
            "5": "Geography",
            "6": "Computer",
            "7": "Politics"
        }

        if choice in subjects:
            return subjects[choice]

        print("\nInvalid choice. Please try again.")


# ==========================================================
# STEP 7 - TOPIC MENU
# ==========================================================

def choose_topic(subject):

    topics = list(RESOURCES[subject].keys())

    while True:

        print("\nChoose a topic:")

        for i, topic in enumerate(topics, 1):
            print(str(i) + ".", topic)

        choice = input("Enter your choice: ").strip()

        if choice.isdigit():

            number = int(choice)

            if 1 <= number <= len(topics):
                return topics[number - 1]

        print("\nInvalid topic choice. Please try again.")


# ==========================================================
# STEP 8 - FIND STUDY RESOURCES
# ==========================================================

def find_resources():

    header("                 FIND STUDY RESOURCES")

    subject = choose_subject()
    topic = choose_topic(subject)

    print("\nSearching for", subject, "-", topic, "...\n")

    print("Recommended resources:")

    for resource in RESOURCES[subject][topic]:
        print("✓", resource)

    print()


# ==========================================================
# STEP 9 - PRACTICE QUIZ
# ==========================================================

def practice_quiz():

    header("                    PRACTICE QUIZ")

    subject = choose_subject()

    print("\nHow many questions do you want?")

    print("1. 5 questions")
    print("2. 10 questions")
    print("3. 15 questions")
    print("4. 25 questions")

    while True:

        choice = input("Enter choice (1-4): ").strip()

        if choice == "1":
            number = 5
            break

        elif choice == "2":
            number = 10
            break

        elif choice == "3":
            number = 15
            break

        elif choice == "4":
            number = 25
            break

        else:
            print("Invalid choice. Please enter 1, 2, 3 or 4.")

    questions = QUIZ[subject]

    print("\nStarting your", number, "question", subject, "quiz!")
    print("All questions in this quiz are unique.\n")

    score = 0

    # ------------------------------------------------------
    # TAKE UNIQUE QUESTIONS
    # ------------------------------------------------------

    for i in range(number):

        q = questions[i]

        print("-----------------------------------------------")
        print("Question", i + 1, "of", number)
        print(q["question"])

        for option in q["options"]:
            print(option)

        while True:

            answer = input("\nYour answer (A/B/C/D): ").strip().upper()

            if answer in ["A", "B", "C", "D"]:
                break

            print("Invalid answer. Please enter A, B, C or D.")

        if answer == q["answer"]:

            print("✓ Correct!")
            score += 1

        else:

            print("✗ Incorrect.")
            print("Correct answer:", q["answer"])

    # ------------------------------------------------------
    # RESULT
    # ------------------------------------------------------

    print("\n")
    line()

    print("                    QUIZ COMPLETE!")

    line()

    print("Subject:", subject)
    print("Score:", score, "/", number)

    percentage = (score / number) * 100

    print("Percentage:", round(percentage, 1), "%")

    line()

    # ------------------------------------------------------
    # SCORE RECOMMENDATION
    # ------------------------------------------------------

    print("\nStudy Recommendation:")

    if percentage < 50:

        print("📘 Start with the basics.")
        print("Review your notes and try the quiz again.")

    elif percentage < 80:

        print("📗 Good work!")
        print("Practice a few more questions to improve.")

    else:

        print("📙 Excellent!")
        print("You can move to more challenging questions.")

    print()


# ==========================================================
# STEP 10 - ASK A DOUBT
# ==========================================================

def ask_doubt():

    header("                    ASK A DOUBT")

    topics = list(DOUBTS.keys())

    print("Choose a topic:\n")

    for i, topic in enumerate(topics, 1):
        print(str(i) + ".", topic)

    while True:

        choice = input("\nEnter your choice: ").strip()

        if choice.isdigit():

            number = int(choice)

            if 1 <= number <= len(topics):

                topic = topics[number - 1]

                print("\n" + "-" * 60)
                print("TOPIC:", topic)
                print("-" * 60)

                print("\nHere's a simple explanation:\n")
                print(DOUBTS[topic])

                print()

                return

        print("Invalid choice. Please try again.")


# ==========================================================
# STEP 11 - SMART RECOMMENDATION
# ==========================================================

def smart_recommendation():

    header("                 SMART RECOMMENDATION")

    print("What do you want to improve?")

    print("1. I am weak in this topic")
    print("2. I need quick revision")
    print("3. I want more practice")
    print("4. I want to prepare for a test")

    while True:

        choice = input("Enter choice (1-4): ").strip()

        if choice == "1":

            print("\nRecommendation:")
            print("1. Start with Easy Notes.")
            print("2. Study examples.")
            print("3. Practice questions.")
            print("4. Take a short quiz.")

            break

        elif choice == "2":

            print("\nRecommendation:")
            print("1. Review Key Points.")
            print("2. Revise important definitions.")
            print("3. Finish with 5 quiz questions.")

            break

        elif choice == "3":

            print("\nRecommendation:")
            print("1. Try Practice Questions.")
            print("2. Check your mistakes.")
            print("3. Attempt a 10-question quiz.")

            break

        elif choice == "4":

            print("\nRecommendation:")
            print("Step 1: Revise notes.")
            print("Step 2: Practice questions.")
            print("Step 3: Take a 15-question quiz.")
            print("Step 4: Review your mistakes.")

            break

        else:

            print("Invalid choice. Please try again.")

    print()


# ==========================================================
# STEP 12 - PERSONALIZED STUDY PLAN
# ==========================================================

def study_plan():

    header("                 PERSONALIZED STUDY PLAN")

    print("How much time do you have today?")

    print("1. 5 minutes")
    print("2. 10 minutes")
    print("3. 15 minutes")
    print("4. 20 minutes")
    print("5. 30 minutes")

    while True:

        choice = input("Enter choice (1-5): ").strip()

        if choice == "1":

            print("\n5-MINUTE PLAN")
            print("1 minute  - Read key points")
            print("2 minutes - Revise important concepts")
            print("2 minutes - Take a quick quiz")
            break

        elif choice == "2":

            print("\n10-MINUTE PLAN")
            print("3 minutes - Read easy notes")
            print("4 minutes - Practice questions")
            print("3 minutes - Quick quiz")
            break

        elif choice == "3":

            print("\n15-MINUTE PLAN")
            print("5 minutes - Learn the concept")
            print("5 minutes - Practice")
            print("5 minutes - Take a quiz")
            break

        elif choice == "4":

            print("\n20-MINUTE PLAN")
            print("7 minutes - Study notes")
            print("7 minutes - Solve questions")
            print("6 minutes - Take a quiz")
            break

        elif choice == "5":

            print("\n30-MINUTE PLAN")
            print("10 minutes - Learn the topic")
            print("10 minutes - Practice questions")
            print("5 minutes - Take a quiz")
            print("5 minutes - Review mistakes")
            break

        else:

            print("Invalid choice. Please try again.")

    print()


# ==========================================================
# STEP 13 - MAIN MENU
# ==========================================================

def menu():

    print("\n")

    line()

    print("                    MAIN MENU")

    line()

    print("1. Find Study Resources")
    print("2. Practice Quiz")
    print("3. Ask a Doubt")
    print("4. Smart Recommendation")
    print("5. Personalized Study Plan")
    print("6. Exit")

    line()


# ==========================================================
# STEP 14 - MAIN PROGRAM
# ==========================================================

def main():

    name = welcome()

    while True:

        menu()

        choice = input("Choose an option (1-6): ").strip()

        if choice == "1":

            find_resources()

        elif choice == "2":

            practice_quiz()

        elif choice == "3":

            ask_doubt()

        elif choice == "4":

            smart_recommendation()

        elif choice == "5":

            study_plan()

        elif choice == "6":

            print("\nThank you for using StudySmart AI,", name + "!")
            print("Keep learning. Keep improving. 🚀")
            break

        else:

            print("\n⚠️ Invalid choice.")
            print("Please enter a number from 1 to 6.")


# ==========================================================
# GUI APPLICATION
# ==========================================================

class StudySmartApp:

    def __init__(self, root):
        self.root = root
        self.root.title("StudySmart AI")
        self.root.geometry("1040x700")
        self.root.minsize(850, 560)
        self.root.configure(bg="#f4f7fb")

        self.name = "Student"
        self.quiz_questions = []
        self.quiz_index = 0
        self.quiz_score = 0
        self.quiz_attempts = 0
        self.best_score = 0
        self.selected_answer = tk.StringVar()

        self._configure_styles()
        self._build_shell()
        self.show_dashboard()

    def _configure_styles(self):
        style = ttk.Style()
        style.theme_use("clam")
        style.configure("TButton", font=("Segoe UI", 11), padding=(12, 8))
        style.configure("Accent.TButton", background="#2563eb", foreground="white")
        style.map("Accent.TButton", background=[("active", "#1d4ed8")])
        style.configure("TCombobox", padding=6)

    def _build_shell(self):
        header = tk.Frame(self.root, bg="#17324d", height=92)
        header.pack(fill="x")
        header.pack_propagate(False)
        brand = tk.Frame(header, bg="#17324d")
        brand.pack(side="left", padx=28, pady=14)
        tk.Label(brand, text="STUDYSMART AI", font=("Segoe UI", 23, "bold"),
             fg="white", bg="#17324d").pack(anchor="w")
        tk.Label(brand, text="Learn with clarity. Grow with confidence.",
             font=("Segoe UI", 10), fg="#b9d8f5", bg="#17324d").pack(anchor="w")
        self.user_badge = tk.Label(header, text="Student", font=("Segoe UI", 10, "bold"),
                       fg="#17324d", bg="#d7e9f8", padx=14, pady=7)
        self.user_badge.pack(side="right", padx=28)

        body = tk.Frame(self.root, bg="#f4f7fb")
        body.pack(fill="both", expand=True)

        self.sidebar = tk.Frame(body, bg="#102a43", width=220)
        self.sidebar.pack(side="left", fill="y")
        self.sidebar.pack_propagate(False)
        tk.Label(self.sidebar, text="LEARN", font=("Segoe UI", 9, "bold"),
                 fg="#8fb3d1", bg="#102a43").pack(anchor="w", padx=22, pady=(24, 8))
        self.nav_buttons = {}
        self._nav_button("Dashboard", self.show_dashboard)
        self._nav_button("Study Resources", self.show_resources)
        self._nav_button("Practice Quiz", self.show_quiz_setup)
        self._nav_button("Ask a Doubt", self.show_doubt)
        self._nav_button("Recommendations", self.show_recommendation)
        self._nav_button("Study Plan", self.show_plan)

        tk.Label(self.sidebar, text="7 subjects  |  175 questions", font=("Segoe UI", 9),
                 fg="#7f9db8", bg="#102a43").pack(side="bottom", padx=18, pady=22)

        self.content = tk.Frame(body, bg="#f4f7fb")
        self.content.pack(side="left", fill="both", expand=True, padx=34, pady=28)

    def _nav_button(self, text, command):
        button = tk.Button(self.sidebar, text=text, command=command, anchor="w",
                           font=("Segoe UI", 11), fg="white", bg="#102a43",
                           activebackground="#245174", activeforeground="white",
                           relief="flat", borderwidth=0, padx=22, pady=11)
        button.pack(fill="x")
        self.nav_buttons[text] = button

    def _set_active(self, name):
        for label, button in self.nav_buttons.items():
            button.configure(bg="#245174" if label == name else "#102a43")

    def _clear(self):
        for widget in self.content.winfo_children():
            widget.destroy()

    def _title(self, heading, subtitle):
        tk.Label(self.content, text=heading, font=("Segoe UI", 24, "bold"),
                 fg="#17324d", bg="#f4f7fb").pack(anchor="w")
        tk.Label(self.content, text=subtitle, font=("Segoe UI", 11),
                 fg="#60758a", bg="#f4f7fb").pack(anchor="w", pady=(4, 22))

    def _card(self, title, text, command):
        card = tk.Frame(self.content, bg="white", highlightbackground="#d8e2ec",
                        highlightthickness=1)
        card.pack(fill="x", pady=7)
        inner = tk.Frame(card, bg="white")
        inner.pack(fill="x", padx=20, pady=17)
        tk.Label(inner, text=title, font=("Segoe UI", 14, "bold"),
                 fg="#17324d", bg="white").pack(anchor="w")
        tk.Label(inner, text=text, font=("Segoe UI", 10), fg="#60758a",
                 bg="white", wraplength=650, justify="left").pack(anchor="w", pady=(5, 12))
        ttk.Button(inner, text="Open", command=command, style="Accent.TButton").pack(anchor="w")

    def show_dashboard(self):
        self._clear()
        self._set_active("Dashboard")
        self.user_badge.configure(text=self.name)
        hero = tk.Frame(self.content, bg="#2563eb")
        hero.pack(fill="x", pady=(0, 18))
        tk.Label(hero, text="Welcome back, " + self.name, font=("Segoe UI", 24, "bold"),
                 fg="white", bg="#2563eb").pack(anchor="w", padx=24, pady=(20, 2))
        tk.Label(hero, text="Make today a little smarter.", font=("Segoe UI", 12),
                 fg="#dbeafe", bg="#2563eb").pack(anchor="w", padx=26, pady=(0, 20))
        form = tk.Frame(self.content, bg="#e7f1fb")
        form.pack(fill="x", pady=(0, 16))
        tk.Label(form, text="Student name", bg="#e7f1fb", fg="#17324d",
                 font=("Segoe UI", 10, "bold")).pack(side="left", padx=(18, 8), pady=15)
        name_var = tk.StringVar(value=self.name if self.name != "Student" else "")
        entry = ttk.Entry(form, textvariable=name_var, width=24)
        entry.pack(side="left", pady=15)
        def save_name():
            self.name = name_var.get().strip() or "Student"
            self.show_dashboard()
        ttk.Button(form, text="Save", command=save_name).pack(side="left", padx=8)
        stats = tk.Frame(self.content, bg="#f4f7fb")
        stats.pack(fill="x", pady=(0, 12))
        self._stat_card(stats, "Subjects", "7", 0)
        self._stat_card(stats, "Quiz attempts", str(self.quiz_attempts), 1)
        self._stat_card(stats, "Best score", str(self.best_score) + "%", 2)
        actions = tk.Frame(self.content, bg="#f4f7fb")
        actions.pack(fill="x")
        self._action_tile(actions, "Study Resources", "Browse notes and revision topics", self.show_resources, 0)
        self._action_tile(actions, "Practice Quiz", "Build a quick confidence check", self.show_quiz_setup, 1)
        self._action_tile(actions, "Ask a Doubt", "Get a simple explanation", self.show_doubt, 2)

    def _stat_card(self, parent, title, value, column):
        card = tk.Frame(parent, bg="white", highlightbackground="#d8e2ec", highlightthickness=1)
        card.grid(row=0, column=column, sticky="nsew", padx=(0 if column == 0 else 8, 8 if column < 2 else 0))
        parent.grid_columnconfigure(column, weight=1)
        tk.Label(card, text=value, bg="white", fg="#2563eb", font=("Segoe UI", 20, "bold")).pack(anchor="w", padx=16, pady=(12, 0))
        tk.Label(card, text=title, bg="white", fg="#60758a", font=("Segoe UI", 9)).pack(anchor="w", padx=16, pady=(0, 12))

    def _action_tile(self, parent, title, text, command, column):
        tile = tk.Frame(parent, bg="white", highlightbackground="#d8e2ec", highlightthickness=1)
        tile.grid(row=0, column=column, sticky="nsew", padx=(0 if column == 0 else 8, 8 if column < 2 else 0))
        parent.grid_columnconfigure(column, weight=1)
        tk.Label(tile, text=title, bg="white", fg="#17324d", font=("Segoe UI", 12, "bold")).pack(anchor="w", padx=16, pady=(15, 2))
        tk.Label(tile, text=text, bg="white", fg="#60758a", font=("Segoe UI", 9), wraplength=190, justify="left").pack(anchor="w", padx=16, pady=(0, 12))
        ttk.Button(tile, text="Open", command=command, style="Accent.TButton").pack(anchor="w", padx=16, pady=(0, 15))

    def _subject_combo(self, parent):
        variable = tk.StringVar(value=list(RESOURCES)[0])
        combo = ttk.Combobox(parent, textvariable=variable, values=list(RESOURCES),
                             state="readonly", width=24)
        combo.pack(anchor="w", pady=(5, 16))
        return variable, combo

    def show_resources(self):
        self._clear()
        self._set_active("Study Resources")
        self._title("Study Resources", "Select a subject and topic to see recommended resources.")
        panel = tk.Frame(self.content, bg="white", highlightbackground="#d8e2ec", highlightthickness=1)
        panel.pack(fill="x", pady=5)
        inner = tk.Frame(panel, bg="white")
        inner.pack(fill="x", padx=24, pady=22)
        tk.Label(inner, text="Subject", bg="white", fg="#17324d", font=("Segoe UI", 10, "bold")).pack(anchor="w")
        subject, subject_combo = self._subject_combo(inner)
        tk.Label(inner, text="Topic", bg="white", fg="#17324d", font=("Segoe UI", 10, "bold")).pack(anchor="w")
        topic = tk.StringVar()
        topic_combo = ttk.Combobox(inner, textvariable=topic, state="readonly", width=24)
        topic_combo.pack(anchor="w", pady=(5, 18))
        result = tk.Label(self.content, text="", bg="#f4f7fb", fg="#17324d",
                          font=("Segoe UI", 12), justify="left", anchor="w", wraplength=700)
        result.pack(fill="x", pady=18)
        def refresh_topics(event=None):
            values = list(RESOURCES[subject.get()])
            topic_combo["values"] = values
            topic.set(values[0])
        subject_combo.bind("<<ComboboxSelected>>", refresh_topics)
        refresh_topics()
        def display():
            resources = RESOURCES[subject.get()][topic.get()]
            result.config(text=subject.get() + " / " + topic.get() + "\n\n" +
                          "\n".join("- " + item for item in resources))
        ttk.Button(inner, text="Show resources", command=display, style="Accent.TButton").pack(anchor="w")

    def show_quiz_setup(self):
        self._clear()
        self._set_active("Practice Quiz")
        self._title("Practice Quiz", "Choose a subject and quiz length. Questions will not repeat.")
        panel = tk.Frame(self.content, bg="white", highlightbackground="#d8e2ec", highlightthickness=1)
        panel.pack(fill="x", pady=5)
        inner = tk.Frame(panel, bg="white")
        inner.pack(fill="x", padx=24, pady=22)
        tk.Label(inner, text="Subject", bg="white", fg="#17324d", font=("Segoe UI", 10, "bold")).pack(anchor="w")
        subject, _ = self._subject_combo(inner)
        tk.Label(inner, text="Number of questions", bg="white", fg="#17324d", font=("Segoe UI", 10, "bold")).pack(anchor="w")
        length = tk.IntVar(value=5)
        ttk.Combobox(inner, textvariable=length, values=[5, 10, 15, 25], state="readonly", width=22).pack(anchor="w", pady=(5, 20))
        ttk.Button(inner, text="Start quiz", command=lambda: self.start_quiz(subject.get(), length.get()), style="Accent.TButton").pack(anchor="w")

    def start_quiz(self, subject, length):
        self.quiz_questions = random.sample(QUIZ[subject], length)
        self.quiz_subject = subject
        self.quiz_index = 0
        self.quiz_score = 0
        self.quiz_attempts += 1
        self.show_question()

    def show_question(self):
        self._clear()
        question = self.quiz_questions[self.quiz_index]
        self._title("Practice Quiz: " + self.quiz_subject,
                    "Question " + str(self.quiz_index + 1) + " of " + str(len(self.quiz_questions)))
        panel = tk.Frame(self.content, bg="white", highlightbackground="#d8e2ec", highlightthickness=1)
        panel.pack(fill="x", pady=5)
        inner = tk.Frame(panel, bg="white")
        inner.pack(fill="x", padx=26, pady=26)
        tk.Label(inner, text=question["question"], bg="white", fg="#17324d",
                 font=("Segoe UI", 15, "bold"), wraplength=700, justify="left").pack(anchor="w", pady=(0, 18))
        self.selected_answer.set("")
        for option in question["options"]:
            ttk.Radiobutton(inner, text=option, value=option[0], variable=self.selected_answer).pack(anchor="w", pady=6)
        ttk.Button(inner, text="Submit answer", command=self.submit_answer, style="Accent.TButton").pack(anchor="w", pady=(18, 0))

    def submit_answer(self):
        if not self.selected_answer.get():
            messagebox.showinfo("Choose an answer", "Please select A, B, C or D.")
            return
        if self.selected_answer.get() == self.quiz_questions[self.quiz_index]["answer"]:
            self.quiz_score += 1
        self.quiz_index += 1
        if self.quiz_index == len(self.quiz_questions):
            self.show_quiz_result()
        else:
            self.show_question()

    def show_quiz_result(self):
        self._clear()
        total = len(self.quiz_questions)
        percentage = self.quiz_score / total * 100
        self.best_score = max(self.best_score, round(percentage))
        self._title("Quiz Complete", "Here is your result for " + self.quiz_subject + ".")
        tk.Label(self.content, text=str(self.quiz_score) + " / " + str(total), bg="#f4f7fb",
                 fg="#2563eb", font=("Segoe UI", 46, "bold")).pack(pady=15)
        tk.Label(self.content, text="Score: " + str(round(percentage, 1)) + "%", bg="#f4f7fb",
                 fg="#17324d", font=("Segoe UI", 16, "bold")).pack(pady=5)
        advice = "Start with the basics and try again." if percentage < 50 else "Good work. Keep practising!" if percentage < 80 else "Excellent! Try a harder challenge next."
        tk.Label(self.content, text=advice, bg="#f4f7fb", fg="#60758a", font=("Segoe UI", 12)).pack(pady=8)
        ttk.Button(self.content, text="New quiz", command=self.show_quiz_setup, style="Accent.TButton").pack(pady=18)

    def show_doubt(self):
        self._clear()
        self._set_active("Ask a Doubt")
        self._title("Ask a Doubt", "Choose a topic and get a simple explanation.")
        topic = tk.StringVar(value=list(DOUBTS)[0])
        ttk.Combobox(self.content, textvariable=topic, values=list(DOUBTS), state="readonly", width=28).pack(anchor="w")
        answer = tk.Label(self.content, text="", bg="#f4f7fb", fg="#17324d", font=("Segoe UI", 13),
                          wraplength=720, justify="left", anchor="w")
        answer.pack(fill="x", pady=28)
        ttk.Button(self.content, text="Explain this topic", command=lambda: answer.config(text=DOUBTS[topic.get()]), style="Accent.TButton").pack(anchor="w")

    def show_recommendation(self):
        self._clear()
        self._set_active("Recommendations")
        self._title("Smart Recommendation", "Tell StudySmart what kind of help you need.")
        choice = tk.StringVar(value="I am weak in this topic")
        values = list({"I am weak in this topic": "Start with easy notes, study examples, practise questions, then take a short quiz.", "I need quick revision": "Review key points and definitions, then finish with 5 quiz questions.", "I want more practice": "Try practice questions, check mistakes, and attempt a 10-question quiz.", "I want to prepare for a test": "Revise notes, practise questions, take a 15-question quiz, and review mistakes."})
        recommendations = {values[0]: "Start with easy notes, study examples, practise questions, then take a short quiz.", values[1]: "Review key points and definitions, then finish with 5 quiz questions.", values[2]: "Try practice questions, check mistakes, and attempt a 10-question quiz.", values[3]: "Revise notes, practise questions, take a 15-question quiz, and review mistakes."}
        ttk.Combobox(self.content, textvariable=choice, values=values, state="readonly", width=34).pack(anchor="w")
        result = tk.Label(self.content, text="", bg="#f4f7fb", fg="#17324d", font=("Segoe UI", 13), wraplength=720, justify="left")
        result.pack(anchor="w", pady=28)
        ttk.Button(self.content, text="Get recommendation", command=lambda: result.config(text=recommendations[choice.get()]), style="Accent.TButton").pack(anchor="w")

    def show_plan(self):
        self._clear()
        self._set_active("Study Plan")
        self._title("Personalized Study Plan", "Choose how much time you have today.")
        plans = {5: "1 minute: Read key points\n2 minutes: Revise concepts\n2 minutes: Take a quick quiz", 10: "3 minutes: Read easy notes\n4 minutes: Practise questions\n3 minutes: Quick quiz", 15: "5 minutes: Learn the concept\n5 minutes: Practise\n5 minutes: Take a quiz", 20: "7 minutes: Study notes\n7 minutes: Solve questions\n6 minutes: Take a quiz", 30: "10 minutes: Learn the topic\n10 minutes: Practise questions\n5 minutes: Take a quiz\n5 minutes: Review mistakes"}
        minutes = tk.IntVar(value=15)
        ttk.Combobox(self.content, textvariable=minutes, values=list(plans), state="readonly", width=24).pack(anchor="w")
        result = tk.Label(self.content, text="", bg="#f4f7fb", fg="#17324d", font=("Segoe UI", 13), justify="left", anchor="w")
        result.pack(fill="x", pady=28)
        ttk.Button(self.content, text="Build my plan", command=lambda: result.config(text=str(minutes.get()) + "-MINUTE PLAN\n\n" + plans[minutes.get()]), style="Accent.TButton").pack(anchor="w")


def gui_main():
    root = tk.Tk()
    StudySmartApp(root)
    root.mainloop()


# ==========================================================
# PROGRAM START
# ==========================================================

if __name__ == "__main__":
    gui_main()
