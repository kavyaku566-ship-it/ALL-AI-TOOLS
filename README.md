```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>AI Tools Hub — Curated Artificial Intelligence Directory</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet" />
  <style>
    :root {
      --bg-primary: #060b19;
      --bg-secondary: #0b132b;
      --bg-card: #111c3d;
      --bg-card-hover: #16244e;
      --border-subtle: rgba(148, 163, 184, 0.14);
      --border-glow: rgba(56, 189, 248, 0.45);
      --text-primary: #f8fafc;
      --text-secondary: #94a3b8;
      --text-muted: #64748b;
      --accent-blue: #38bdf8;
      --accent-indigo: #6366f1;
      --accent-purple: #a855f7;
      --accent-emerald: #10b981;
      --accent-amber: #f59e0b;
      --gradient-brand: linear-gradient(135deg, #38bdf8 0%, #6366f1 55%, #a855f7 100%);
      --shadow-card: 0 10px 30px -10px rgba(2, 6, 23, 0.75);
      --shadow-glow: 0 0 30px rgba(56, 189, 248, 0.18);
      --radius-lg: 16px;
      --radius-md: 12px;
      --radius-pill: 9999px;
      --transition: all 0.25s cubic-bezier(0.4, 0, 0.2, 1);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
      background-color: var(--bg-primary);
      color: var(--text-primary);
      line-height: 1.6;
      overflow-x: hidden;
      background-image:
        radial-gradient(circle at 15% 10%, rgba(56, 189, 248, 0.08) 0%, transparent 35%),
        radial-gradient(circle at 85% 25%, rgba(99, 102, 241, 0.09) 0%, transparent 40%),
        radial-gradient(circle at 50% 80%, rgba(168, 85, 247, 0.06) 0%, transparent 45%);
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    ul {
      list-style: none;
    }

    .container {
      width: 100%;
      max-width: 1240px;
      margin: 0 auto;
      padding: 0 1.25rem;
    }

    /* ================= NAVBAR ================= */
    header {
      position: sticky;
      top: 0;
      z-index: 1000;
      background: rgba(6, 11, 25, 0.85);
      backdrop-filter: blur(14px);
      -webkit-backdrop-filter: blur(14px);
      border-bottom: 1px solid var(--border-subtle);
    }

    .nav-wrapper {
      display: flex;
      align-items: center;
      justify-content: space-between;
      height: 72px;
    }

    .logo {
      display: flex;
      align-items: center;
      gap: 0.65rem;
      font-weight: 800;
      font-size: 1.25rem;
      letter-spacing: -0.02em;
    }

    .logo-icon {
      width: 36px;
      height: 36px;
      border-radius: 10px;
      background: var(--gradient-brand);
      display: grid;
      place-items: center;
      font-weight: 800;
      font-size: 1rem;
      color: #fff;
      box-shadow: 0 4px 16px rgba(99, 102, 241, 0.45);
    }

    .logo span {
      background: var(--gradient-brand);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 2rem;
    }

    .nav-links a {
      font-size: 0.95rem;
      font-weight: 500;
      color: var(--text-secondary);
      transition: var(--transition);
      position: relative;
    }

    .nav-links a:hover,
    .nav-links a.active {
      color: var(--text-primary);
    }

    .nav-links a::after {
      content: '';
      position: absolute;
      left: 0;
      bottom: -6px;
      width: 0;
      height: 2px;
      background: var(--gradient-brand);
      border-radius: 2px;
      transition: var(--transition);
    }

    .nav-links a:hover::after,
    .nav-links a.active::after {
      width: 100%;
    }

    .nav-actions {
      display: flex;
      align-items: center;
      gap: 0.75rem;
    }

    .saved-counter-btn {
      display: inline-flex;
      align-items: center;
      gap: 0.4rem;
      padding: 0.5rem 0.9rem;
      border-radius: var(--radius-pill);
      background: var(--bg-secondary);
      border: 1px solid var(--border-subtle);
      color: var(--text-secondary);
      font-size: 0.85rem;
      font-weight: 600;
      cursor: pointer;
      transition: var(--transition);
    }

    .saved-counter-btn:hover,
    .saved-counter-btn.active {
      border-color: var(--accent-amber);
      color: var(--accent-amber);
    }

    .nav-cta {
      padding: 0.55rem 1.15rem;
      border-radius: var(--radius-pill);
      background: rgba(56, 189, 248, 0.12);
      border: 1px solid rgba(56, 189, 248, 0.35);
      color: var(--accent-blue);
      font-weight: 600;
      font-size: 0.875rem;
      cursor: pointer;
      transition: var(--transition);
    }

    .nav-cta:hover {
      background: var(--accent-blue);
      color: #060b19;
    }

    .mobile-toggle {
      display: none;
      background: transparent;
      border: 1px solid var(--border-subtle);
      color: var(--text-primary);
      padding: 0.45rem 0.65rem;
      border-radius: 8px;
      cursor: pointer;
      font-size: 1.25rem;
    }

    /* ================= HERO SECTION ================= */
    .hero {
      padding: 5.5rem 0 4rem;
      text-align: center;
    }

    .hero-badge {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      padding: 0.4rem 1rem;
      border-radius: var(--radius-pill);
      background: rgba(99, 102, 241, 0.14);
      border: 1px solid rgba(99, 102, 241, 0.35);
      color: #a5b4fc;
      font-size: 0.82rem;
      font-weight: 600;
      margin-bottom: 1.5rem;
    }

    .hero-badge .dot {
      width: 8px;
      height: 8px;
      border-radius: 50%;
      background: var(--accent-blue);
      box-shadow: 0 0 10px var(--accent-blue);
    }

    .hero h1 {
      font-size: clamp(2.2rem, 5vw, 3.75rem);
      font-weight: 800;
      line-height: 1.12;
      letter-spacing: -0.03em;
      max-width: 820px;
      margin: 0 auto 1.25rem;
    }

    .hero h1 .gradient-text {
      background: var(--gradient-brand);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .hero p {
      font-size: 1.1rem;
      color: var(--text-secondary);
      max-width: 640px;
      margin: 0 auto 2.5rem;
    }

    /* Search Box */
    .search-wrapper {
      max-width: 680px;
      margin: 0 auto 2.75rem;
      position: relative;
    }

    .search-box {
      display: flex;
      align-items: center;
      background: var(--bg-secondary);
      border: 1px solid rgba(148, 163, 184, 0.25);
      border-radius: var(--radius-pill);
      padding: 0.45rem 0.5rem 0.45rem 1.35rem;
      box-shadow: 0 16px 40px -12px rgba(2, 6, 23, 0.85);
      transition: var(--transition);
    }

    .search-box:focus-within {
      border-color: var(--accent-blue);
      box-shadow: 0 0 0 4px rgba(56, 189, 248, 0.15), 0 16px 40px -12px rgba(2, 6, 23, 0.85);
    }

    .search-icon {
      color: var(--text-muted);
      margin-right: 0.75rem;
      flex-shrink: 0;
    }

    .search-box input {
      flex: 1;
      background: transparent;
      border: none;
      outline: none;
      color: var(--text-primary);
      font-size: 1rem;
      font-family: inherit;
      min-width: 0;
    }

    .search-box input::placeholder {
      color: var(--text-muted);
    }

    .clear-btn {
      background: transparent;
      border: none;
      color: var(--text-muted);
      cursor: pointer;
      padding: 0.35rem 0.65rem;
      font-size: 0.85rem;
      display: none;
    }

    .clear-btn:hover {
      color: var(--text-primary);
    }

    .search-submit {
      background: var(--gradient-brand);
      border: none;
      color: #fff;
      font-weight: 600;
      font-size: 0.92rem;
      padding: 0.7rem 1.45rem;
      border-radius: var(--radius-pill);
      cursor: pointer;
      transition: var(--transition);
      flex-shrink: 0;
    }

    .search-submit:hover {
      opacity: 0.92;
      transform: translateY(-1px);
    }

    .hero-stats {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      gap: 2.5rem;
      padding-top: 1rem;
    }

    .stat-item {
      text-align: center;
    }

    .stat-number {
      font-size: 1.55rem;
      font-weight: 800;
      color: var(--text-primary);
    }

    .stat-label {
      font-size: 0.82rem;
      color: var(--text-muted);
      text-transform: uppercase;
      letter-spacing: 0.06em;
    }

    /* ================= TOOLS DIRECTORY SECTION ================= */
    .section {
      padding: 4.5rem 0;
    }

    .section-header {
      display: flex;
      flex-wrap: wrap;
      align-items: flex-end;
      justify-content: space-between;
      gap: 1.25rem;
      margin-bottom: 2.25rem;
    }

    .section-tag {
      font-size: 0.8rem;
      font-weight: 700;
      text-transform: uppercase;
      letter-spacing: 0.1em;
      color: var(--accent-blue);
      margin-bottom: 0.4rem;
      display: block;
    }

    .section-title {
      font-size: clamp(1.65rem, 3vw, 2.25rem);
      font-weight: 800;
      letter-spacing: -0.02em;
    }

    .results-count {
      font-size: 0.9rem;
      color: var(--text-secondary);
      background: var(--bg-secondary);
      padding: 0.45rem 0.95rem;
      border-radius: var(--radius-pill);
      border: 1px solid var(--border-subtle);
    }

    /* Filter Bar */
    .filter-controls {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: space-between;
      gap: 1rem;
      margin-bottom: 2rem;
    }

    .category-pills {
      display: flex;
      flex-wrap: wrap;
      gap: 0.6rem;
    }

    .pill-btn {
      padding: 0.55rem 1.15rem;
      border-radius: var(--radius-pill);
      background: var(--bg-secondary);
      border: 1px solid var(--border-subtle);
      color: var(--text-secondary);
      font-family: inherit;
      font-size: 0.9rem;
      font-weight: 600;
      cursor: pointer;
      transition: var(--transition);
      display: inline-flex;
      align-items: center;
      gap: 0.45rem;
    }

    .pill-btn:hover {
      border-color: rgba(56, 189, 248, 0.4);
      color: var(--text-primary);
    }

    .pill-btn.active {
      background: var(--gradient-brand);
      border-color: transparent;
      color: #fff;
      box-shadow: 0 6px 20px rgba(99, 102, 241, 0.35);
    }

    .sort-select {
      background: var(--bg-secondary);
      border: 1px solid var(--border-subtle);
      color: var(--text-primary);
      padding: 0.55rem 1rem;
      border-radius: var(--radius-md);
      font-family: inherit;
      font-size: 0.88rem;
      outline: none;
      cursor: pointer;
    }

    /* Tools Grid */
    .tools-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(290px, 1fr));
      gap: 1.5rem;
    }

    .tool-card {
      background: var(--bg-card);
      border: 1px solid var(--border-subtle);
      border-radius: var(--radius-lg);
      padding: 1.5rem;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      box-shadow: var(--shadow-card);
      transition: var(--transition);
      position: relative;
      overflow: hidden;
    }

    .tool-card::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      height: 3px;
      background: var(--gradient-brand);
      opacity: 0;
      transition: var(--transition);
    }

    .tool-card:hover {
      transform: translateY(-5px);
      background: var(--bg-card-hover);
      border-color: var(--border-glow);
      box-shadow: var(--shadow-card), var(--shadow-glow);
    }

    .tool-card:hover::before {
      opacity: 1;
    }

    .card-top {
      display: flex;
      align-items: flex-start;
      justify-content: space-between;
      gap: 0.75rem;
      margin-bottom: 1rem;
    }

    .tool-identity {
      display: flex;
      align-items: center;
      gap: 0.85rem;
    }

    .tool-avatar {
      width: 46px;
      height: 46px;
      border-radius: 12px;
      display: grid;
      place-items: center;
      font-size: 1.35rem;
      font-weight: 700;
      flex-shrink: 0;
      background: rgba(56, 189, 248, 0.12);
      border: 1px solid rgba(56, 189, 248, 0.25);
    }

    .tool-title-wrap h3 {
      font-size: 1.1rem;
      font-weight: 700;
      color: var(--text-primary);
      line-height: 1.25;
    }

    .tool-category-badge {
      display: inline-block;
      margin-top: 0.25rem;
      font-size: 0.73rem;
      font-weight: 600;
      text-transform: uppercase;
      letter-spacing: 0.05em;
      padding: 0.18rem 0.55rem;
      border-radius: 6px;
    }

    .cat-image { background: rgba(168, 85, 247, 0.16); color: #d8b4fe; }
    .cat-video { background: rgba(244, 63, 94, 0.16); color: #fda4af; }
    .cat-writing { background: rgba(16, 185, 129, 0.16); color: #6ee7b7; }
    .cat-coding { background: rgba(56, 189, 248, 0.16); color: #7dd3fc; }
    .cat-audio { background: rgba(245, 158, 11, 0.16); color: #fcd34d; }

    .bookmark-btn {
      background: rgba(15, 23, 42, 0.6);
      border: 1px solid var(--border-subtle);
      color: var(--text-secondary);
      width: 34px;
      height: 34px;
      border-radius: 8px;
      display: grid;
      place-items: center;
      cursor: pointer;
      transition: var(--transition);
      flex-shrink: 0;
      font-size: 1rem;
    }

    .bookmark-btn:hover,
    .bookmark-btn.saved {
      color: var(--accent-amber);
      border-color: rgba(245, 158, 11, 0.45);
      background: rgba(245, 158, 11, 0.12);
    }

    .tool-desc {
      font-size: 0.92rem;
      color: var(--text-secondary);
      margin-bottom: 1.25rem;
      display: -webkit-box;
      -webkit-line-clamp: 3;
      -webkit-box-orient: vertical;
      overflow: hidden;
    }

    .tool-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 0.4rem;
      margin-bottom: 1.35rem;
    }

    .tool-tag {
      font-size: 0.75rem;
      color: var(--text-muted);
      background: rgba(6, 11, 25, 0.55);
      border: 1px solid var(--border-subtle);
      padding: 0.2rem 0.55rem;
      border-radius: 6px;
    }

    .card-footer {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding-top: 1rem;
      border-top: 1px solid var(--border-subtle);
      gap: 0.75rem;
    }

    .pricing-pill {
      font-size: 0.78rem;
      font-weight: 600;
      padding: 0.25rem 0.65rem;
      border-radius: var(--radius-pill);
      background: rgba(148, 163, 184, 0.12);
      color: #cbd5e1;
    }

    .card-actions {
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .btn-details {
      background: transparent;
      border: 1px solid var(--border-subtle);
      color: var(--text-secondary);
      padding: 0.45rem 0.75rem;
      border-radius: 8px;
      font-size: 0.82rem;
      font-weight: 600;
      cursor: pointer;
      transition: var(--transition);
    }

    .btn-details:hover {
      color: var(--text-primary);
      border-color: var(--text-secondary);
    }

    .btn-visit {
      background: rgba(56, 189, 248, 0.14);
      border: 1px solid rgba(56, 189, 248, 0.35);
      color: var(--accent-blue);
      padding: 0.45rem 0.85rem;
      border-radius: 8px;
      font-size: 0.82rem;
      font-weight: 600;
      display: inline-flex;
      align-items: center;
      gap: 0.35rem;
      transition: var(--transition);
    }

    .btn-visit:hover {
      background: var(--accent-blue);
      color: #060b19;
    }

    .empty-state {
      grid-column: 1 / -1;
      text-align: center;
      padding: 4rem 1.5rem;
      background: var(--bg-secondary);
      border: 1px dashed var(--border-subtle);
      border-radius: var(--radius-lg);
    }

    .empty-state h3 {
      font-size: 1.25rem;
      margin-bottom: 0.5rem;
    }

    .empty-state p {
      color: var(--text-secondary);
      margin-bottom: 1.25rem;
    }

    /* ================= ABOUT SECTION ================= */
    .about-section {
      background: linear-gradient(180deg, rgba(11, 19, 43, 0.4) 0%, rgba(11, 19, 43, 0.9) 100%);
      border-top: 1px solid var(--border-subtle);
      border-bottom: 1px solid var(--border-subtle);
    }

    .about-grid {
      display: grid;
      grid-template-columns: 1.1fr 0.9fr;
      gap: 3rem;
      align-items: center;
    }

    .about-content h2 {
      font-size: clamp(1.75rem, 3vw, 2.35rem);
      font-weight: 800;
      margin-bottom: 1rem;
      line-height: 1.2;
    }

    .about-content p {
      color: var(--text-secondary);
      margin-bottom: 1.25rem;
      font-size: 1rem;
    }

    .feature-list {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1rem;
      margin-top: 1.75rem;
    }

    .feature-box {
      background: var(--bg-card);
      border: 1px solid var(--border-subtle);
      border-radius: var(--radius-md);
      padding: 1.15rem;
    }

    .feature-box h4 {
      font-size: 0.98rem;
      margin-bottom: 0.35rem;
      color: var(--text-primary);
    }

    .feature-box p {
      font-size: 0.85rem;
      margin-bottom: 0;
      color: var(--text-secondary);
    }

    .about-visual {
      background: var(--bg-card);
      border: 1px solid var(--border-subtle);
      border-radius: var(--radius-lg);
      padding: 2rem;
      box-shadow: var(--shadow-card);
    }

    .metric-row {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1rem 0;
      border-bottom: 1px solid var(--border-subtle);
    }

    .metric-row:last-child {
      border-bottom: none;
      padding-bottom: 0;
    }

    .metric-row:first-child {
      padding-top: 0;
    }

    .metric-info h4 {
      font-size: 1rem;
      font-weight: 700;
    }

    .metric-info span {
      font-size: 0.83rem;
      color: var(--text-secondary);
    }

    .metric-badge {
      font-weight: 800;
      font-size: 1.1rem;
      color: var(--accent-blue);
      background: rgba(56, 189, 248, 0.12);
      padding: 0.35rem 0.8rem;
      border-radius: 8px;
    }

    /* ================= CONTACT / SUBMIT SECTION ================= */
    .contact-wrapper {
      display: grid;
      grid-template-columns: 1fr 1.2fr;
      gap: 2.5rem;
      background: var(--bg-secondary);
      border: 1px solid var(--border-subtle);
      border-radius: var(--radius-lg);
      padding: 2.5rem;
      box-shadow: var(--shadow-card);
    }

    .contact-info h2 {
      font-size: 1.9rem;
      font-weight: 800;
      margin-bottom: 0.75rem;
    }

    .contact-info p {
      color: var(--text-secondary);
      margin-bottom: 2rem;
    }

    .contact-details {
      display: flex;
      flex-direction: column;
      gap: 1.1rem;
    }

    .contact-item {
      display: flex;
      align-items: center;
      gap: 0.9rem;
      color: var(--text-secondary);
      font-size: 0.95rem;
    }

    .contact-icon {
      width: 40px;
      height: 40px;
      border-radius: 10px;
      background: rgba(56, 189, 248, 0.12);
      color: var(--accent-blue);
      display: grid;
      place-items: center;
      font-size: 1.1rem;
      flex-shrink: 0;
    }

    .contact-form {
      display: flex;
      flex-direction: column;
      gap: 1.1rem;
    }

    .form-row {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1rem;
    }

    .form-group {
      display: flex;
      flex-direction: column;
      gap: 0.4rem;
    }

    .form-group label {
      font-size: 0.85rem;
      font-weight: 600;
      color: var(--text-secondary);
    }

    .form-group input,
    .form-group select,
    .form-group textarea {
      background: var(--bg-primary);
      border: 1px solid var(--border-subtle);
      border-radius: 10px;
      padding: 0.75rem 0.95rem;
      col
