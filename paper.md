<style>
  html { scroll-behavior: smooth; }
  
  /* The "Desk" Background */
  body {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, Arial, sans-serif;
    line-height: 1.8;
    color: #334155;
    margin: 0;
    display: flex;
    background-color: #e2e8f0; /* Darker slate gray desk */
  }

  /* Left Sidebar Navigation */
  .sidebar {
    position: fixed;
    top: 0;
    left: 0;
    width: 260px;
    height: 100vh;
    background: #1e293b; /* Deep slate dark mode sidebar */
    padding: 2.5rem 1.5rem;
    box-sizing: border-box;
    overflow-y: auto;
    box-shadow: 4px 0 10px rgba(0,0,0,0.1);
  }
  .sidebar h3 {
    font-size: 0.9em;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    color: #94a3b8;
    margin-bottom: 1.5rem;
  }
  .sidebar a {
    display: block;
    text-decoration: none;
    color: #f8fafc;
    font-weight: 500;
    padding: 0.6rem 1rem;
    border-radius: 8px;
    margin-bottom: 0.4rem;
    transition: all 0.2s ease;
  }
  .sidebar a:hover {
    background-color: #3b82f6; /* Bright blue hover */
    color: #ffffff;
    transform: translateX(4px);
  }

  /* The "Paper" Container */
  .content {
    margin-left: 280px; /* Push past sidebar */
    margin-top: 2rem;
    margin-bottom: 3rem;
    padding: 4rem 5rem;
    max-width: 850px;
    background: #ffffff;
    border-radius: 12px;
    box-shadow: 0 20px 25px -5px rgba(0,0,0,0.1), 0 10px 10px -5px rgba(0,0,0,0.04); /* Deep page shadow */
    border-top: 6px solid #1e3a8a; /* Deep academic navy accent line */
  }

  h1 {
    font-size: 2.6em;
    font-weight: 800;
    color: #0f172a;
    line-height: 1.2;
    margin-bottom: 0.5em;
  }
  h2 {
    font-size: 1.6em;
    color: #1e3a8a; /* Deep Navy Headers */
    border-bottom: 2px solid #cbd5e1;
    padding-bottom: 0.4em;
    margin-top: 2.5em;
    scroll-margin-top: 2rem;
  }
  
  /* Unique Metadata Badges */
  .meta-banner {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    margin: 2rem 0;
    padding-bottom: 2rem;
    border-bottom: 1px solid #e2e8f0;
  }
  .meta-badge {
    background: #f1f5f9;
    padding: 0.5rem 1rem;
    border-radius: 6px;
    font-size: 0.9em;
    color: #475569;
    font-weight: 500;
    border: 1px solid #cbd5e1;
  }
  .meta-badge strong {
    color: #0f172a;
    margin-right: 0.5rem;
  }

  /* Callout Boxes */
  .abstract-box {
    background-color: #eff6ff; /* Very light blue */
    border-left: 4px solid #3b82f6;
    padding: 2rem;
    margin: 2rem 0;
    border-radius: 0 8px 8px 0;
    font-style: italic;
    color: #1e3a8a;
  }

  /* Colored Data Tables */
  table {
    width: 100%;
    border-collapse: collapse;
    margin: 2rem 0;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 4px 6px -1px rgba(0,0,0,0.1);
  }
  th {
    background-color: #1e3a8a; /* Navy table header */
    text-align: left;
    padding: 14px;
    font-weight: 600;
    color: #ffffff; 
  }
  td {
    padding: 14px;
    border-bottom: 1px solid #e2e8f0;
    background-color: #f8fafc;
  }
  tr:hover td {
    background-color: #f1f5f9; /* Slight highlight on row hover */
  }
</style>
