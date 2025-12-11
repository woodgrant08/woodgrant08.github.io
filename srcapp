import React, { useState } from "react";
import Timer from "./components/Timer.jsx";
import HPIChat from "./components/HPIChat.jsx";
import ExamFindings from "./components/ExamFindings.jsx";
import AdditionalTests from "./components/AdditionalTests.jsx";
import DiagnosisPlan from "./components/DiagnosisPlan.jsx";
import Grading from "./components/Grading.jsx";
import case1 from "./data/case1.json";

export default function App() {
  const [section, setSection] = useState(1);
  const [hpiLog, setHpiLog] = useState([]);
  const [testsRequested, setTestsRequested] = useState([]);
  const [diagnosis, setDiagnosis] = useState("");
  const [plan, setPlan] = useState("");
  const [score, setScore] = useState(null);

  return (
    <div className="max-w-5xl mx-auto p-6 space-y-6">
      <Timer />

      {section === 1 && (
        <div className="border border-gray-700 p-6 rounded-xl">
          <h1 className="text-2xl font-semibold mb-4">Case Encounter</h1>
          <p><strong>Chief Complaint:</strong> {case1.chiefComplaint}</p>
          <p><strong>History of Present Illness:</strong> {case1.history}</p>

          <button
            className="mt-6 px-4 py-2 bg-blue-600 rounded-lg"
            onClick={() => setSection(2)}
          >
            Continue to HPI Questions
          </button>
        </div>
      )}

      {section === 2 && (
        <HPIChat
          hpiLog={hpiLog}
          setHpiLog={setHpiLog}
          next={() => setSection(3)}
        />
      )}

      {section === 3 && (
        <ExamFindings next={() => setSection(4)} />
      )}

      {section === 4 && (
        <AdditionalTests
          testsRequested={testsRequested}
          setTestsRequested={setTestsRequested}
          next={() => setSection(5)}
        />
      )}

      {section === 5 && (
        <DiagnosisPlan
          diagnosis={diagnosis}
          setDiagnosis={setDiagnosis}
          plan={plan}
          setPlan={setPlan}
          next={() => setSection(6)}
        />
      )}

      {section === 6 && (
        <Grading
          hpiLog={hpiLog}
          testsRequested={testsRequested}
          diagnosis={diagnosis}
          plan={plan}
          score={score}
          setScore={setScore}
        />
      )}
    </div>
  );
}
