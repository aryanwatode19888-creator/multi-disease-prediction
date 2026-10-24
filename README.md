# multi-disease-prediction
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>AI-Driven Multi-Disease Risk Prediction & Early Symptom Assessment</title>
  <style>
    /* -------------------------------------------------------------
       College Project: Multi-Disease Risk Prediction System
       Frontend: Pure HTML5 + CSS3 + Vanilla JavaScript
       Ready for direct hosting on GitHub Pages (No compiler needed!)
       ------------------------------------------------------------- */
    :root {
      --primary: #0f766e;
      --primary-dark: #115e59;
      --primary-light: #ccfbf1;
      --accent: #2563eb;
      --bg: #f8fafc;
      --card-bg: #ffffff;
      --text-main: #0f172a;
      --text-muted: #64748b;
      --border: #e2e8f0;
      --low-bg: #dcfce7;
      --med-bg: #fef3c7;
      --high-bg: #fee2e2;
      --radius: 12px;
      --shadow: 0 4px 6px -1px rgba(0,0,0,0.06);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
    }

    body {
      background-color: var(--bg);
      color: var(--text-main);
      line-height: 1.6;
      padding-bottom: 60px;
    }

    /* Disclaimer Bar */
    .disclaimer-banner {
      background-color: #fffbeb;
      border-bottom: 1px solid #fde68a;
      color: #92400e;
      padding: 10px 20px;
      font-size: 0.88rem;
      text-align: center;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
    }

    /* Header */
    header {
      background: linear-gradient(135deg, #042f2e 0%, #0f766e 100%);
      color: #ffffff;
      padding: 40px 20px 30px;
      text-align: center;
    }
    header h1 {
      font-size: 2rem;
      font-weight: 800;
      letter-spacing: -0.025em;
      margin-bottom: 8px;
    }
    header p {
      font-size: 1rem;
      color: #ccfbf1;
      max-width: 780px;
      margin: 0 auto 16px;
    }
    .badge-container {
      display: flex;
      justify-content: center;
      gap: 10px;
      flex-wrap: wrap;
    }
    .badge {
      background: rgba(255,255,255,0.18);
      border: 1px solid rgba(255,255,255,0.25);
      border-radius: 9999px;
      padding: 4px 14px;
      font-size: 0.8rem;
      font-weight: 600;
    }

    /* Main Container */
    .container {
      max-width: 1020px;
      margin: 30px auto 0;
      padding: 0 20px;
    }

    /* Navigation Tabs */
    .tabs-nav {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 8px;
      background: #e2e8f0;
      padding: 6px;
      border-radius: var(--radius);
      margin-bottom: 24px;
    }
    .tab-btn {
      background: transparent;
      border: none;
      padding: 12px 14px;
      font-size: 0.95rem;
      font-weight: 600;
      color: var(--text-muted);
      border-radius: 8px;
      cursor: pointer;
      transition: all 0.2s ease;
    }
    .tab-btn:hover {
      color: var(--text-main);
      background: rgba(255, 255, 255, 0.6);
    }
    .tab-btn.active {
      background: #ffffff;
      color: var(--primary);
      box-shadow: 0 2px 4px rgba(0,0,0,0.06);
    }

    /* Cards */
    .card {
      background: var(--card-bg);
      border-radius: var(--radius);
      border: 1px solid var(--border);
      box-shadow: var(--shadow);
      padding: 28px;
      margin-bottom: 24px;
    }
    .card-header {
      margin-bottom: 20px;
      border-bottom: 1px solid var(--border);
      padding-bottom: 14px;
    }
    .card-header h2 {
      font-size: 1.35rem;
      font-weight: 700;
    }
    .card-header p {
      font-size: 0.9rem;
      color: var(--text-muted);
      margin-top: 4px;
    }

    /* Form Grid */
    .form-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
      gap: 20px;
    }
    .form-group {
      display: flex;
      flex-direction: column;
      gap: 6px;
    }
    label {
      font-size: 0.88rem;
      font-weight: 600;
      color: #334155;
    }
    .helper-text {
      font-size: 0.78rem;
      color: var(--text-muted);
    }
    input[type="number"], select {
      padding: 10px 14px;
      border: 1px solid var(--border);
      border-radius: 8px;
      font-size: 0.95rem;
      color: var(--text-main);
      background: #ffffff;
    }
    input[type="number"]:focus, select:focus {
      outline: none;
      border-color: var(--primary);
      box-shadow: 0 0 0 3px rgba(15, 118, 110, 0.15);
    }

    /* Quick Presets */
    .presets-row {
      display: flex;
      gap: 10px;
      align-items: center;
      margin-bottom: 20px;
      flex-wrap: wrap;
    }
    .presets-row span {
      font-size: 0.85rem;
      font-weight: 600;
      color: var(--text-muted);
    }
    .preset-chip {
      background: #f1f5f9;
      border: 1px solid #cbd5e1;
      padding: 4px 12px;
      border-radius: 6px;
      font-size: 0.82rem;
      font-weight: 500;
      cursor: pointer;
      color: #334155;
    }
    .preset-chip:hover {
      background: #e2e8f0;
    }

    /* Buttons */
    .actions-row {
      margin-top: 28px;
      display: flex;
      gap: 12px;
      justify-content: flex-end;
    }
    .btn {
      padding: 11px 22px;
      font-size: 0.95rem;
      font-weight: 600;
      border-radius: 8px;
      cursor: pointer;
      border: none;
      transition: all 0.15s ease;
    }
    .btn-primary {
      background-color: var(--primary);
      color: #ffffff;
    }
    .btn-primary:hover {
      background-color: var(--primary-dark);
    }
    .btn-secondary {
      background: #f1f5f9;
      color: #475569;
      border: 1px solid #cbd5e1;
    }

    /* Results Card */
    #resultsSection {
      display: none;
      animation: fadeIn 0.3s ease-out;
    }
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(8px); }
      to { opacity: 1; transform: translateY(0); }
    }
    .risk-banner {
      padding: 22px;
      border-radius: var(--radius);
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 20px;
      flex-wrap: wrap;
      gap: 16px;
    }
    .risk-banner.low {
      background-color: var(--low-bg);
      border: 1px solid #86efac;
      color: #166534;
    }
    .risk-banner.medium {
      background-color: var(--med-bg);
      border: 1px solid #fde047;
      color: #854d0e;
    }
    .risk-banner.high {
      background-color: var(--high-bg);
      border: 1px solid #fca5a5;
      color: #991b1b;
    }
    .risk-percent {
      font-size: 2.4rem;
      font-weight: 900;
    }

    /* Table */
    .factors-table {
      width: 100%;
      border-collapse: collapse;
      margin: 16px 0;
      font-size: 0.9rem;
    }
    .factors-table th, .factors-table td {
      padding: 10px 14px;
      text-align: left;
      border-bottom: 1px solid var(--border);
    }
    .factors-table th {
      background: #f8fafc;
      color: #475569;
      font-weight: 600;
    }
    .status-badge {
      display: inline-block;
      padding: 2px 10px;
      border-radius: 9999px;
      font-size: 0.75rem;
      font-weight: 700;
    }
    .status-badge.normal { background: #dcfce7; color: #15803d; }
    .status-badge.borderline { background: #fef3c7; color: #b45309; }
    .status-badge.high { background: #fee2e2; color: #b91c1c; }

    /* Symptoms */
    .symptom-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 14px;
    }
    .symptom-item {
      display: flex;
      align-items: flex-start;
      gap: 12px;
      padding: 14px;
      border: 1px solid var(--border);
      border-radius: 8px;
      background: #ffffff;
      cursor: pointer;
    }
    .symptom-item:hover {
      border-color: var(--primary);
      background: #f0fdfa;
    }
    .symptom-item input[type="checkbox"] {
      margin-top: 4px;
      accent-color: var(--primary);
      width: 18px;
      height: 18px;
    }

    /* Rec List */
    .rec-list {
      list-style-type: none;
      display: flex;
      flex-direction: column;
      gap: 10px;
      margin-top: 10px;
    }
    .rec-list li {
      position: relative;
      padding-left: 24px;
      font-size: 0.92rem;
      color: #334155;
    }
    .rec-list li::before {
      content: "✓";
      position: absolute;
      left: 0;
      color: var(--primary);
      font-weight: bold;
    }

    @media (max-width: 768px) {
      .tabs-nav { grid-template-columns: repeat(2, 1fr); }
      header h1 { font-size: 1.5rem; }
      .card { padding: 18px; }
    }
  </style>
</head>
<body>

  <!-- Disclaimer Banner -->
  <aside class="disclaimer-banner">
    <span>⚠️ <strong>Educational Prototype:</strong> This system is a student engineering model demonstration. It is <strong>NOT</strong> a certified medical diagnostic tool.</span>
  </aside>

  <!-- Header -->
  <header>
    <h1>AI-Driven Multi-Disease Risk Prediction System</h1>
    <p>Early symptom assessment, transparent risk stratification, and machine learning decision support for diabetes, heart disease, and liver health.</p>
    <div class="badge-container">
      <span class="badge">Computer Engineering Project</span>
      <span class="badge">Frontend: HTML5 & CSS3</span>
      <span class="badge">Flask API Ready</span>
      <span class="badge">Hosted on GitHub Pages</span>
    </div>
  </header>

  <main class="container">
    <!-- Disease Navigation Tabs -->
    <nav class="tabs-nav" aria-label="Assessment Navigation">
      <button class="tab-btn active" onclick="switchTab('diabetes')">🩺 Diabetes</button>
      <button class="tab-btn" onclick="switchTab('heart')">❤️ Heart Disease</button>
      <button class="tab-btn" onclick="switchTab('liver')">🔬 Liver Disease</button>
      <button class="tab-btn" onclick="switchTab('symptoms')">📋 Symptom Checker</button>
    </nav>

    <!-- SECTION 1: DIABETES -->
    <section id="diabetesSection" class="card">
      <div class="card-header">
        <h2>Type-2 Diabetes Risk Assessment</h2>
        <p>Grounded in clinical attributes aligned with the Pima Indians Diabetes benchmark dataset.</p>
      </div>

      <div class="presets-row">
        <span>Load Test Cases:</span>
        <button type="button" class="preset-chip" onclick="loadDiabetesPreset('healthy')">Healthy Normal</button>
        <button type="button" class="preset-chip" onclick="loadDiabetesPreset('prediabetic')">Borderline Prediabetes</button>
        <button type="button" class="preset-chip" onclick="loadDiabetesPreset('highrisk')">High Risk Profile</button>
      </div>

      <form id="diabetesForm" onsubmit="assessDiabetes(event)">
        <div class="form-grid">
          <div class="form-group">
            <label for="diab_age">Age (Years)</label>
            <input type="number" id="diab_age" required min="10" max="100" value="38">
            <span class="helper-text">Adults ≥ 45 carry higher baseline risk</span>
          </div>
          <div class="form-group">
            <label for="diab_glucose">Fasting Blood Glucose (mg/dL)</label>
            <input type="number" id="diab_glucose" required min="50" max="350" value="95">
            <span class="helper-text">Normal: 70–99 | Prediabetes: 100–125 | Diabetic: ≥126</span>
          </div>
          <div class="form-group">
            <label for="diab_bp">Systolic Blood Pressure (mm Hg)</label>
            <input type="number" id="diab_bp" required min="70" max="220" value="118">
            <span class="helper-text">Optimal: &lt;120 | Elevated: 120–139 | High: ≥140</span>
          </div>
          <div class="form-group">
            <label for="diab_bmi">Body Mass Index (BMI)</label>
            <input type="number" id="diab_bmi" step="0.1" required min="12" max="60" value="23.4">
            <span class="helper-text">Healthy: 18.5 – 24.9 | Overweight: 25 – 29.9</span>
          </div>
          <div class="form-group">
            <label for="diab_insulin">2-Hour Serum Insulin (μU/mL)</label>
            <input type="number" id="diab_insulin" min="0" max="800" value="79">
            <span class="helper-text">Normal fasting: 16 – 166 μU/mL</span>
          </div>
          <div class="form-group">
            <label for="diab_family">Family History of Diabetes</label>
            <select id="diab_family">
              <option value="no">No First-Degree Relative</option>
              <option value="yes">Yes (Parent or Sibling)</option>
            </select>
            <span class="helper-text">Genetic predisposition indicator</span>
          </div>
        </div>

        <div class="actions-row">
          <button type="reset" class="btn btn-secondary">Clear Form</button>
          <button type="submit" class="btn btn-primary">Calculate Diabetes Risk</button>
        </div>
      </form>
    </section>

    <!-- SECTION 2: HEART DISEASE -->
    <section id="heartSection" class="card" style="display: none;">
      <div class="card-header">
        <h2>Cardiovascular Disease Risk Assessment</h2>
        <p>Based on Framingham & Cleveland Heart Disease clinical parameters.</p>
      </div>

      <div class="presets-row">
        <span>Load Test Cases:</span>
        <button type="button" class="preset-chip" onclick="loadHeartPreset('healthy')">Young Healthy</button>
        <button type="button" class="preset-chip" onclick="loadHeartPreset('moderate')">Moderate Lipids</button>
        <button type="button" class="preset-chip" onclick="loadHeartPreset('highrisk')">High Cardiac Risk</button>
      </div>

      <form id="heartForm" onsubmit="assessHeart(event)">
        <div class="form-grid">
          <div class="form-group">
            <label for="heart_age">Age (Years)</label>
            <input type="number" id="heart_age" required min="18" max="95" value="42">
          </div>
          <div class="form-group">
            <label for="heart_gender">Biological Sex</label>
            <select id="heart_gender">
              <option value="male">Male</option>
              <option value="female">Female</option>
            </select>
          </div>
          <div class="form-group">
            <label for="heart_bp">Resting Blood Pressure (mm Hg)</label>
            <input type="number" id="heart_bp" required min="80" max="220" value="122">
            <span class="helper-text">Systolic measurement at rest</span>
          </div>
          <div class="form-group">
            <label for="heart_chol">Serum Cholesterol (mg/dL)</label>
            <input type="number" id="heart_chol" required min="100" max="500" value="190">
            <span class="helper-text">Desirable: &lt;200 | Borderline: 200–239 | High: ≥240</span>
          </div>
          <div class="form-group">
            <label for="heart_pain">Chest Pain Type</label>
            <select id="heart_pain">
              <option value="non-anginal">Non-Anginal Discomfort</option>
              <option value="atypical">Atypical Angina</option>
              <option value="typical">Typical Exertional Angina</option>
              <option value="asymptomatic">Asymptomatic</option>
            </select>
          </div>
          <div class="form-group">
            <label for="heart_hr">Max Heart Rate Achieved (bpm)</label>
            <input type="number" id="heart_hr" required min="60" max="220" value="155">
          </div>
          <div class="form-group">
            <label for="heart_angina">Exercise-Induced Angina</label>
            <select id="heart_angina">
              <option value="no">No</option>
              <option value="yes">Yes</option>
            </select>
          </div>
          <div class="form-group">
            <label for="heart_oldpeak">ST Depression (Oldpeak in mm)</label>
            <input type="number" id="heart_oldpeak" step="0.1" required min="0" max="6.2" value="0.8">
          </div>
        </div>

        <div class="actions-row">
          <button type="reset" class="btn btn-secondary">Clear Form</button>
          <button type="submit" class="btn btn-primary">Calculate Cardiac Risk</button>
        </div>
      </form>
    </section>

    <!-- SECTION 3: LIVER DISEASE -->
    <section id="liverSection" class="card" style="display: none;">
      <div class="card-header">
        <h2>Hepatic & Liver Function Risk Assessment</h2>
        <p>Modeled after the Indian Liver Patient Dataset (ILPD) biochemistry markers.</p>
      </div>

      <div class="presets-row">
        <span>Load Test Cases:</span>
        <button type="button" class="preset-chip" onclick="loadLiverPreset('healthy')">Normal Enzymes</button>
        <button type="button" class="preset-chip" onclick="loadLiverPreset('elevated')">Mild Transaminitis</button>
        <button type="button" class="preset-chip" onclick="loadLiverPreset('highrisk')">Jaundice / Acute Stress</button>
      </div>

      <form id="liverForm" onsubmit="assessLiver(event)">
        <div class="form-grid">
          <div class="form-group">
            <label for="liver_age">Age (Years)</label>
            <input type="number" id="liver_age" required min="10" max="95" value="35">
          </div>
          <div class="form-group">
            <label for="liver_tb">Total Bilirubin (mg/dL)</label>
            <input type="number" id="liver_tb" step="0.1" required min="0.1" max="25" value="0.8">
            <span class="helper-text">Normal: 0.1 – 1.2 mg/dL</span>
          </div>
          <div class="form-group">
            <label for="liver_db">Direct Bilirubin (mg/dL)</label>
            <input type="number" id="liver_db" step="0.1" required min="0" max="15" value="0.2">
            <span class="helper-text">Normal: 0.0 – 0.3 mg/dL</span>
          </div>
          <div class="form-group">
            <label for="liver_alp">Alkaline Phosphatase (IU/L)</label>
            <input type="number" id="liver_alp" required min="30" max="1200" value="110">
            <span class="helper-text">Normal: 44 – 147 IU/L</span>
          </div>
          <div class="form-group">
            <label for="liver_alt">ALT / SGPT (IU/L)</label>
            <input type="number" id="liver_alt" required min="5" max="800" value="28">
            <span class="helper-text">Normal liver enzyme: 7 – 56 IU/L</span>
          </div>
          <div class="form-group">
            <label for="liver_ast">AST / SGOT (IU/L)</label>
            <input type="number" id="liver_ast" required min="5" max="800" value="31">
            <span class="helper-text">Normal: 10 – 40 IU/L</span>
          </div>
          <div class="form-group">
            <label for="liver_alb">Serum Albumin (g/dL)</label>
            <input type="number" id="liver_alb" step="0.1" required min="1.0" max="6.0" value="4.2">
            <span class="helper-text">Normal: 3.5 – 5.0 g/dL</span>
          </div>
          <div class="form-group">
            <label for="liver_alcohol">Alcohol Intake Profile</label>
            <select id="liver_alcohol">
              <option value="none">None / Rare</option>
              <option value="moderate">Moderate</option>
              <option value="heavy">Frequent / Chronic</option>
            </select>
          </div>
        </div>

        <div class="actions-row">
          <button type="reset" class="btn btn-secondary">Clear Form</button>
          <button type="submit" class="btn btn-primary">Calculate Liver Risk</button>
        </div>
      </form>
    </section>

    <!-- SECTION 4: SYMPTOM CHECKER -->
    <section id="symptomsSection" class="card" style="display: none;">
      <div class="card-header">
        <h2>Early Warning Symptom Assessment Checklist</h2>
        <p>Check any current symptoms to evaluate potential early metabolic, cardiac, or hepatic risks.</p>
      </div>

      <div class="symptom-grid">
        <label class="symptom-item">
          <input type="checkbox" name="sym" value="polyuria" data-disease="diabe