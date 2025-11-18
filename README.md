
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Power of Small Habits</title>
    <style>
        :root {
            --bg-color: #f0f4f8;
            --container-bg: #ffffff;
            --text-primary: #2d3748;
            --text-secondary: #4a5568;
            --accent-color: #319795; /* Teal */
            --accent-light: #e6fffa;
            --border-color: #e2e8f0;
            --font-heading: 'Georgia', serif;
            --font-body: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        html, body {
            overflow-x: hidden; /* Prevent horizontal scroll from full-bleed elements */
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-primary);
            font-family: var(--font-body);
            line-height: 1.7;
            font-size: 18px;
            -webkit-font-smoothing: antialiased;
            -webkit-text-size-adjust: 100%; /* Prevent font resizing on orientation change */
        }

        /* Layout & Container */
        .container {
            max-width: 800px;
            margin: 0 auto;
            background-color: var(--container-bg);
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
        }

        /* Header Section */
        header {
            background: linear-gradient(135deg, #285e61 0%, #319795 100%);
            color: white;
            padding: 5rem 2rem;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        h1 {
            font-family: var(--font-heading);
            font-size: 2.8rem;
            margin-bottom: 1rem;
            line-height: 1.2;
            position: relative;
            z-index: 10;
            word-wrap: break-word; /* Prevent overflow on small screens */
        }

        .subtitle {
            font-size: 1.25rem;
            opacity: 0.95;
            font-weight: 300;
            margin-bottom: 1.5rem;
            position: relative;
            z-index: 10;
        }

        .meta {
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 2px;
            opacity: 0.8;
            border-top: 1px solid rgba(255,255,255,0.3);
            display: inline-block;
            padding-top: 1rem;
            position: relative;
            z-index: 10;
        }

        /* Main Content */
        main {
            padding: 4rem 3rem;
        }

        /* Typography */
        h2 {
            font-family: var(--font-heading);
            color: #2c3e50;
            font-size: 2rem;
            margin-top: 3rem;
            margin-bottom: 1.5rem;
            border-left: 5px solid var(--accent-color);
            padding-left: 1rem;
        }

        h3 {
            font-size: 1.4rem;
            margin-top: 2rem;
            margin-bottom: 1rem;
            color: var(--text-primary);
        }

        p {
            margin-bottom: 1.8rem;
            color: var(--text-secondary);
        }

        strong {
            color: #285e61;
            font-weight: 700;
        }

        /* Images */
        .img-wrapper {
            width: 100%;
            margin: 3rem 0;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
            position: relative;
            background-color: #f0f4f8; /* Placeholder color while loading */
        }

        img {
            width: 100%;
            height: auto;
            display: block;
            transition: transform 0.5s ease;
        }

        .img-wrapper:hover img {
            transform: scale(1.03);
        }

        .caption {
            text-align: center;
            font-size: 0.9rem;
            color: #718096;
            padding: 0.8rem;
            background: #f7fafc;
            border-top: 1px solid #edf2f7;
            font-style: italic;
        }

        /* Blockquote */
        blockquote {
            background-color: var(--accent-light);
            border-left: 6px solid var(--accent-color);
            padding: 2rem;
            margin: 3rem 0;
            font-family: var(--font-heading);
            font-size: 1.2rem;
            font-style: italic;
            color: #234e52;
            border-radius: 0 12px 12px 0;
            box-shadow: 0 4px 6px -1px rgba(0,0,0,0.05);
        }

        blockquote small {
            display: block;
            margin-top: 1rem;
            font-size: 0.9rem;
            font-family: var(--font-body);
            font-style: normal;
            color: #319795;
            font-weight: bold;
        }

        /* Lists */
        .habit-steps {
            list-style: none;
            padding-left: 0;
            counter-reset: step-counter;
            display: grid;
            grid-template-columns: 1fr;
            gap: 1.5rem;
        }

        .habit-steps li {
            background: white;
            border: 1px solid var(--border-color);
            padding: 1.5rem 1.5rem 1.5rem 4rem;
            border-radius: 10px;
            position: relative;
            box-shadow: 0 2px 4px rgba(0,0,0,0.02);
            transition: transform 0.2s;
        }

        .habit-steps li:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 6px rgba(0,0,0,0.05);
            border-color: var(--accent-color);
        }

        .habit-steps li::before {
            content: counter(step-counter);
            counter-increment: step-counter;
            position: absolute;
            left: 1rem;
            top: 1.5rem;
            width: 2rem;
            height: 2rem;
            background-color: var(--accent-color);
            color: white;
            border-radius: 50%;
            text-align: center;
            line-height: 2rem;
            font-weight: bold;
            font-size: 1rem;
        }

        .step-title {
            display: block;
            font-weight: 800;
            font-size: 1.1rem;
            color: #2d3748;
            margin-bottom: 0.5rem;
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 4rem 2rem;
            background-color: #1a202c;
            color: #a0aec0;
            font-size: 0.95rem;
        }

        footer p {
            color: #718096;
            margin-bottom: 0;
        }

        /* Mobile Optimization */
        @media (max-width: 768px) {
            /* Container becomes full width on mobile */
            .container {
                box-shadow: none;
            }

            /* Header adjustments */
            header { 
                padding: 4rem 1.5rem; 
            }
            h1 { 
                font-size: 2.2rem; /* Smaller heading */
            }
            .subtitle {
                font-size: 1.1rem;
            }

            /* Main content spacing */
            main { 
                padding: 2rem 1.25rem; 
            }
            
            /* Body Text */
            body { 
                font-size: 17px; 
                line-height: 1.6; /* Slightly tighter line height for mobile */
            }

            /* Headings */
            h2 {
                font-size: 1.6rem;
                margin-top: 2.5rem;
                border-left-width: 4px;
            }

            /* Full-bleed images for mobile app feel */
            .img-wrapper { 
                margin: 2.5rem -1.25rem; /* Negative margin to pull image to edges */
                width: calc(100% + 2.5rem); 
                border-radius: 0; 
            }

            /* Full-bleed blockquote */
            blockquote { 
                margin: 2.5rem -1.25rem; 
                width: calc(100% + 2.5rem); 
                border-radius: 0; 
                padding: 1.5rem;
                font-size: 1.1rem;
                border-left-width: 4px;
            }

            /* List adjustments */
            .habit-steps li {
                padding: 1.25rem 1rem 1.25rem 3.5rem; /* Reduce padding */
            }
            .habit-steps li::before {
                left: 0.75rem;
                top: 1.25rem;
            }
        }

        /* Small Phones optimization */
        @media (max-width: 380px) {
            h1 { font-size: 1.8rem; }
            header { padding: 3rem 1rem; }
            main { padding: 1.5rem 1rem; }
            .img-wrapper, blockquote {
                margin: 2rem -1rem;
                width: calc(100% + 2rem);
            }
        }
    </style>
</head>
<body>

    <div class="container">
        <header>
            <h1>The Power of Small Habits</h1>
            <div class="subtitle">How Tiny Actions Create Massive Change</div>
            <div class="meta">November 09, 2025</div>
        </header>

        <main>
            <!-- Image 1: Growth/Start -->
            <div class="img-wrapper">
                <img src="https://images.unsplash.com/photo-1546518038-d45fb0b33539?q=80&w=1000&auto=format&fit=crop" alt="Small green plant sprout growing from soil in morning light" loading="lazy">
                <div class="caption">Greatness often begins with something incredibly small.</div>
            </div>

            <p>When we think about success, most of us imagine grand gestures — big plans, massive transformations, and life-changing moments. We assume people who achieve great things must have done something extraordinary. But if you look closer, the truth is the opposite: greatness often begins with something incredibly small — a single habit.</p>

            <section>
                <h2>Why Small Habits Matter</h2>
                <p>Habits are the invisible architecture of daily life. Every day, the things we repeatedly do — whether consciously or not — shape who we become. A single workout won’t make you fit, just like skipping one meal won’t make you unhealthy. But repeating that choice every day creates the difference between strength and weakness, growth and stagnation.</p>

                <p>Small habits might seem insignificant at first, but they compound over time. Reading ten pages a day feels minor until a year later, when you’ve absorbed the lessons of a dozen books. Writing a few lines every morning doesn’t look like much, but soon, you’re staring at a completed journal or novel.</p>
                
                <!-- Image 2: Books/Reading -->
                <div class="img-wrapper">
                    <img src="https://images.unsplash.com/photo-1506880018603-83d5b814b5a6?q=80&w=1000&auto=format&fit=crop" alt="A stack of books and reading glasses" loading="lazy">
                    <div class="caption">Consistent reading compounds into massive knowledge over time.</div>
                </div>

                <p>Consistency is the bridge between goals and results. Big ambitions fail not because they’re impossible, but because people try to achieve them all at once. They sprint instead of pacing themselves — and eventually burn out.</p>
            </section>

            <section>
                <h2>The Psychology Behind Tiny Changes</h2>
                <p>Your brain resists change because it values comfort and familiarity. When you try to overhaul your entire routine overnight, your brain interprets it as a threat. That’s why big resolutions often collapse within weeks.</p>

                <p>However, when you start small — say, meditating for two minutes or walking for five — it doesn’t trigger resistance. Over time, your brain adapts, and the small habit becomes part of your identity. You start thinking of yourself as someone who “shows up.” Once that identity forms, improvement becomes natural.</p>

                <!-- Image 3: Journaling/Morning Routine -->
                <div class="img-wrapper">
                    <img src="https://images.unsplash.com/photo-1484555230612-0f2941eb8508?q=80&w=1000&auto=format&fit=crop" alt="Open journal with a cup of coffee on a wooden desk" loading="lazy">
                    <div class="caption">Habit Stacking: Pairing a new habit like journaling with your morning coffee.</div>
                </div>

                <p>This is the same principle used in behavioral science, known as <strong>habit stacking</strong> — attaching a new behavior to an existing one. For example, if you want to start journaling, you can decide, “I’ll write for two minutes right after brushing my teeth.” It’s small, but it works because it builds consistency.</p>
            </section>

            <section>
                <h2>Small Steps, Big Results</h2>
                <p>History and modern success stories prove this. Writers who publish bestselling books often started with a few words a day. Athletes who dominate championships built their strength from daily training sessions. Entrepreneurs who run global businesses once focused on making a single sale.</p>

                <p>The key isn’t speed; it’s direction. Every small step forward — no matter how slow — is still progress. Even one percent improvement each day compounds to remarkable growth over time.</p>

                <blockquote>
                    “You do not rise to the level of your goals. You fall to the level of your systems.”
                    <small>— James Clear, author of Atomic Habits</small>
                </blockquote>

                <p>Goals give you direction, but habits build the system that actually gets you there.</p>
            </section>

            <section>
                <h2>Breaking the Myth of Motivation</h2>
                <p>Most people wait to “feel ready” before they start something new. That’s a trap. Motivation is unreliable — it fades when things get hard. What keeps you moving is <strong>discipline</strong>. The beauty of small habits is that they don’t require huge bursts of motivation. They’re easy enough to do, even on bad days.</p>

                <p>You don’t need to run five kilometers every morning — just start with five minutes of walking. You don’t need to read a whole chapter — read a single page. The hardest part of any habit is starting; once you begin, momentum takes over.</p>
            </section>

            <section>
                <h2>How to Build a Small Habit That Sticks</h2>
                
                <!-- Image 4: Planning/Calendar -->
                <div class="img-wrapper">
                    <img src="https://images.unsplash.com/photo-1506784983877-45594efa4cbe?q=80&w=1000&auto=format&fit=crop" alt="Planning on a calendar with a pen" loading="lazy">
                    <div class="caption">Track your progress visibly to maintain momentum.</div>
                </div>

                <ol class="habit-steps">
                    <li>
                        <div class="step-title">Start Ridiculously Small.</div>
                        Begin with something so easy it feels almost silly. If your goal is to exercise, start with just two push-ups or a one-minute stretch.
                    </li>
                    <li>
                        <div class="step-title">Attach It to an Existing Routine.</div>
                        Link it to something you already do daily — like “after my morning coffee” or “before going to bed.”
                    </li>
                    <li>
                        <div class="step-title">Track It Visibly.</div>
                        Use a notebook, calendar, or app to mark your progress. Seeing your streak grow keeps you motivated.
                    </li>
                    <li>
                        <div class="step-title">Forgive Yourself Quickly.</div>
                        Missing one day won’t ruin your progress. Missing two days might. If you slip, restart immediately.
                    </li>
                    <li>
                        <div class="step-title">Focus on Identity, Not Outcome.</div>
                        Don’t aim to “run a marathon.” Aim to “be a runner.” Identity-based habits last longer than goal-based ones.
                    </li>
                </ol>
            </section>

            <!-- Image 5: Running Shoes/Action -->
            <div class="img-wrapper">
                <img src="https://images.unsplash.com/photo-1552674605-db6ffd4facb5?q=80&w=1000&auto=format&fit=crop" alt="Running shoes on asphalt ready to run" loading="lazy">
                <div class="caption">Focus on the identity: Become a runner, not just someone who runs.</div>
            </div>

            <section>
                <h2>The Real Power: Becoming Consistent</h2>
                <p>The most powerful people aren’t those who work the hardest once — they’re the ones who show up every day, even when it’s boring, tiring, or inconvenient. That quiet persistence is what separates success from failure.</p>

                <p>When you commit to small habits, you’re training your mind for patience, consistency, and resilience. Over time, those little actions create a foundation for bigger dreams.</p>
            </section>

            <section>
                <h2>Final Thoughts</h2>
                <p>Big changes don’t happen overnight. They’re the result of small, steady actions repeated over time. Whether it’s learning a skill, improving your health, or building confidence — the secret isn’t in doing more, but in starting small and never stopping.</p>

                <p>So instead of waiting for the perfect day to change your life, start today — even if it’s just one tiny step. Because that’s how real transformation begins.</p>
            </section>
        </main>

        <footer>
            <p>&copy; 2025 The Power of Small Habits.</p>
        </footer>
    </div>

</body>
</html>
