import streamlit as st
import pandas as pd
from datetime import datetime

st.set_page_config(
    page_title="Software Engineering Learning Portal",
    page_icon="💻",
    layout="wide"
)

# ------------------------------
# Header
# ------------------------------

st.title("💻 Software Engineering Learning Portal")
st.write("Interactive Assignment Portal")
st.caption(f"📅 {datetime.now().strftime('%d-%m-%Y %H:%M:%S')}")

# ------------------------------
# Sidebar
# ------------------------------

st.sidebar.title("📚 Navigation")

page = st.sidebar.radio(
    "Go To",
    [
        "🏠 Home",
        "Problem 1 - Scrum",
        "Problem 2 - Smart Parking",
        "Problem 3 - Lean + XP",
        "Problem 4 - SAFe",
        "Problem 5 - Ethical AI",
        "Quiz",
        "Certificate"
    ]
)

# Progress Tracker
pages = [
    "Problem 1 - Scrum",
    "Problem 2 - Smart Parking",
    "Problem 3 - Lean + XP",
    "Problem 4 - SAFe",
    "Problem 5 - Ethical AI"
]

if "visited" not in st.session_state:
    st.session_state.visited = []

if page in pages and page not in st.session_state.visited:
    st.session_state.visited.append(page)

st.sidebar.write(
    f"✅ Progress: {len(st.session_state.visited)}/5 Problems Viewed"
)

# ------------------------------
# HOME
# ------------------------------

if page == "🏠 Home":

    st.header("Welcome")

    st.write("""
This portal demonstrates:

✅ Agile Methodologies  
✅ Scrum  
✅ Feasibility Studies  
✅ Lean and XP  
✅ SAFe Framework  
✅ Ethical AI
""")

    st.info(
        "Use the sidebar to navigate through all five case studies."
    )

# ------------------------------
# PROBLEM 1
# ------------------------------

elif page == "Problem 1 - Scrum":

    st.header("Problem 1: Applying Scrum in a Telemedicine App Project")

    st.subheader("Scenario")
    st.write(
        "Frequent backlog changes reduce productivity and confuse stakeholders."
    )

    st.subheader("Scrum Roles")

    st.table(pd.DataFrame({
        "Role": [
            "Product Owner",
            "Scrum Master",
            "Development Team"
        ],
        "Responsibility": [
            "Manages Product Backlog",
            "Ensures Scrum practices",
            "Develops and tests software"
        ]
    }))

    st.subheader("Root Cause Analysis")

    st.write("""
• Frequent requirement changes  
• Poor backlog grooming  
• Lack of stakeholder communication  
• Unclear sprint goals
""")

    st.subheader("Backlog Prioritization")

    st.table(pd.DataFrame({
        "Priority": [
            "Must Have",
            "Should Have",
            "Could Have",
            "Won't Have"
        ],
        "Example": [
            "Video Consultation",
            "Prescription Upload",
            "Chatbot Support",
            "Advanced Analytics"
        ]
    }))

    st.subheader("Retrospective Suggestions")

    st.write("""
✅ Weekly backlog refinement

✅ Freeze requirements during sprint

✅ Improve communication

✅ Set clear sprint goals
""")

# ------------------------------
# PROBLEM 2
# ------------------------------

elif page == "Problem 2 - Smart Parking":

    st.header("Problem 2: Feasibility Study for a Smart Parking System")

    st.subheader("Technical Feasibility")

    st.write("""
• Sensors

• Mobile Application

• Cloud Database

• Internet Connectivity
""")

    st.subheader("Operational Feasibility")

    st.write("""
• Easy parking booking

• Reduced traffic

• Better user experience
""")

    st.subheader("Cost-Benefit Estimation")

    df = pd.DataFrame({
        "Item": [
            "Sensors",
            "Mobile App",
            "Server"
        ],
        "Cost": [
            "₹50,000",
            "₹30,000",
            "₹20,000"
        ]
    })

    st.table(df)

    st.success("Total Estimated Cost: ₹1,00,000")

    st.subheader("Design Thinking Activity")

    st.write("""
Conduct user interviews with drivers to understand:

• Parking problems

• Desired features

• User expectations
""")

# ------------------------------
# PROBLEM 3
# ------------------------------

elif page == "Problem 3 - Lean + XP":

    st.header("Problem 3: Lean + XP")

    st.subheader("Lean Wastes")

    st.write("""
• Waiting

• Defects

• Extra features

• Rework

• Delays

• Task switching
""")

    st.subheader("XP Practices")

    st.write("""
• Pair Programming

• Test Driven Development

• Continuous Integration

• Refactoring
""")

    st.subheader("Workflow")

    st.code("""
Requirements
↓
Development
↓
Testing
↓
Deployment
↓
Feedback
""")

    st.subheader("User Story")

    st.info(
        "As a student, I want to book a tutor session so that I can learn online."
    )

    st.subheader("Acceptance Criteria")

    st.write("""
✅ View tutors

✅ Select time slot

✅ Receive booking confirmation
""")

# ------------------------------
# PROBLEM 4
# ------------------------------

elif page == "Problem 4 - SAFe":

    st.header("Problem 4: Scaling Agile Using SAFe")

    st.subheader("Agile Release Train (ART)")

    st.write("""
Multiple Agile teams work together to deliver value continuously.
""")

    st.subheader("Key Roles")

    st.table(pd.DataFrame({
        "Role": [
            "Product Manager",
            "Product Owner",
            "Release Train Engineer",
            "System Architect"
        ]
    }))

    st.subheader("PI Planning Workflow")

    st.code("""
Business Goals
↓
Team Planning
↓
Dependency Identification
↓
Risk Discussion
↓
Commitment
""")

    st.subheader("Risk Mitigation")

    st.table(pd.DataFrame({
        "Risk": [
            "Communication Issues",
            "Requirement Changes",
            "Dependency Conflicts"
        ],
        "Mitigation": [
            "Daily Meetings",
            "Backlog Management",
            "Early Planning"
        ]
    }))

# ------------------------------
# PROBLEM 5
# ------------------------------

elif page == "Problem 5 - Ethical AI":

    st.header("Problem 5: Ethical Evaluation of an AI Hiring System")

    st.subheader("Ethical Issues")

    st.write("""
• Bias against applicant groups

• Unfair decisions

• Lack of transparency
""")

    st.subheader("Data Ethics Actions")

    st.write("""
• Use diverse datasets

• Conduct bias audits

• Human review
""")

    st.subheader("Privacy Risks")

    st.write("""
• Data leakage

• Unauthorized access

• Identity theft

• Excessive data collection
""")

    st.subheader("Ethical Design Measures")

    st.write("""
✅ Encryption

✅ Access control

✅ Responsible AI policies

✅ Regular security audits
""")

# ------------------------------
# QUIZ
# ------------------------------

elif page == "Quiz":

    st.header("Mini Quiz")

    answer = st.text_input(
        "Which framework is used for large-scale Agile?"
    )

    if st.button("Submit"):

        if answer.lower() == "safe":
            st.success("Correct! 🎉")
            st.balloons()

        else:
            st.error("Correct Answer: SAFe")

# ------------------------------
# CERTIFICATE
# ------------------------------

elif page == "Certificate":

    st.header("🎓 Completion Certificate")

    name = st.text_input("Enter Your Name")

    if st.button("Generate Certificate"):

        st.success(
            f"Congratulations {name}!\n\nYou have completed the Software Engineering Learning Portal."
        )

        st.balloons()

# ------------------------------
# Footer
# ------------------------------

st.markdown("---")
st.caption("Developed by Aswitha | Software Engineering Assignment Portal")