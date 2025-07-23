# The-Open-Journal
A simple method for sharing information and collecting and gathering information
<!DOCTYPE html>

<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>The Open Journal</title>

    <style>

        * {

            margin: 0;

            padding: 0;

            box-sizing: border-box;

        }



        body {

            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;

            line-height: 1.6;

            color: #333;

            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);

            min-height: 100vh;

            user-select: none;

            padding-top: 0;

        }



        .watermark {

            position: fixed;

            bottom: 20px;

            right: 20px;

            color: rgba(255, 255, 255, 0.6);

            font-size: 14px;

            font-weight: bold;

            z-index: 1000;

            pointer-events: none;

        }



        .container {

            max-width: 1200px;

            margin: 0 auto;

            padding: 0 20px;

        }



        .header {

            background: rgba(255, 255, 255, 0.95);

            backdrop-filter: blur(10px);

            box-shadow: 0 2px 20px rgba(0, 0, 0, 0.1);

            position: sticky;

            top: 0;

            z-index: 100;

        }



        .nav {

            display: flex;

            justify-content: space-between;

            align-items: center;

            padding: 1rem 0;

        }



        .logo {

            font-size: 2rem;

            font-weight: bold;

            background: linear-gradient(45deg, #667eea, #764ba2);

            -webkit-background-clip: text;

            -webkit-text-fill-color: transparent;

            background-clip: text;

        }



        .nav-buttons {

            display: flex;

            gap: 1rem;

        }



        .btn {

            padding: 0.5rem 1rem;

            border: none;

            border-radius: 25px;

            cursor: pointer;

            font-weight: bold;

            transition: all 0.3s ease;

            text-decoration: none;

            display: inline-block;

        }



        .btn-primary {

            background: linear-gradient(45deg, #667eea, #764ba2);

            color: white;

        }



        .btn-secondary {

            background: transparent;

            color: #667eea;

            border: 2px solid #667eea;

        }



        .btn:hover {

            transform: translateY(-2px);

            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);

        }



        .ribbon {

            background: rgba(255, 255, 255, 0.9);

            padding: 1rem 0;

            margin: 1rem 0;

            border-radius: 15px;

            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);

        }



        .search-container {

            display: flex;

            gap: 1rem;

            align-items: center;

            margin-bottom: 1rem;

        }



        .search-box {

            flex: 1;

            padding: 0.8rem;

            border: 2px solid #ddd;

            border-radius: 25px;

            font-size: 1rem;

            transition: border-color 0.3s ease;

        }



        .search-box:focus {

            outline: none;

            border-color: #667eea;

        }



        .filter-dropdown {

            padding: 0.8rem;

            border: 2px solid #ddd;

            border-radius: 25px;

            background: white;

        }



        .ai-summary-btn {

            background: linear-gradient(45deg, #ff6b6b, #feca57);

            color: white;

            padding: 0.8rem 1.5rem;

            border: none;

            border-radius: 25px;

            cursor: pointer;

            font-weight: bold;

        }



        .main-content {

            background: rgba(255, 255, 255, 0.95);

            border-radius: 15px;

            margin: 2rem 0;

            padding: 2rem;

            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);

        }



        .topic-header {

            text-align: center;

            margin-bottom: 2rem;

        }



        .topic-title {

            font-size: 2.5rem;

            color: #333;

            margin-bottom: 1rem;

        }



        .post {

            background: linear-gradient(135deg, #f8f9fa, #e9ecef);

            border-radius: 15px;

            padding: 1.5rem;

            margin: 1rem 0;

            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);

            transition: transform 0.3s ease;

        }



        .post:hover {

            transform: translateY(-5px);

        }



        .post-header {

            display: flex;

            justify-content: between;

            align-items: center;

            margin-bottom: 1rem;

        }



        .author-info {

            display: flex;

            align-items: center;

            gap: 0.5rem;

        }



        .country-flag {

            width: 24px;

            height: 16px;

            background: #ddd;

            border-radius: 3px;

            display: flex;

            align-items: center;

            justify-content: center;

            font-size: 12px;

        }



        .post-content {

            color: #555;

            line-height: 1.8;

        }



        .poll-section {

            background: linear-gradient(135deg, #74b9ff, #0984e3);

            color: white;

            padding: 2rem;

            border-radius: 15px;

            margin: 2rem 0;

            text-align: center;

        }



        .poll-options {

            display: flex;

            gap: 1rem;

            justify-content: center;

            margin: 1rem 0;

        }



        .poll-option {

            background: rgba(255, 255, 255, 0.2);

            border: 2px solid rgba(255, 255, 255, 0.3);

            color: white;

            padding: 0.8rem 1.5rem;

            border-radius: 25px;

            cursor: pointer;

            transition: all 0.3s ease;

        }



        .poll-option:hover {

            background: rgba(255, 255, 255, 0.3);

        }



        .modal {

            display: none;

            position: fixed;

            top: 0;

            left: 0;

            width: 100%;

            height: 100%;

            background: rgba(0, 0, 0, 0.8);

            z-index: 1000;

        }



        .modal-content {

            background: white;

            width: 90%;

            max-width: 500px;

            margin: 10% auto;

            padding: 2rem;

            border-radius: 15px;

            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);

        }



        .auth-options {

            display: flex;

            flex-direction: column;

            gap: 1rem;

        }



        .auth-btn {

            padding: 1rem;

            border: none;

            border-radius: 10px;

            cursor: pointer;

            font-size: 1rem;

            transition: all 0.3s ease;

        }



        .google-btn {

            background: #db4437;

            color: white;

        }



        .facebook-btn {

            background: #3b5998;

            color: white;

        }



        .phone-btn {

            background: #25d366;

            color: white;

        }



        .email-btn {

            background: #667eea;

            color: white;

        }



        .guest-btn {

            background: #6c757d;

            color: white;

        }



        .ads {

            background: linear-gradient(45deg, #ff9a9e, #fecfef);

            padding: 1rem;

            border-radius: 10px;

            margin: 1rem 0;

            text-align: center;

            color: #333;

            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);

            transition: transform 0.3s ease;

            cursor: pointer;

        }



        .ads:hover {

            transform: translateY(-3px);

            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);

        }



        /* Responsive ads */

        @media (max-width: 768px) {

            div[style*="position: fixed"][style*="right: 20px"] {

                display: none;

            }

            

            div[style*="position: fixed"][style*="top: 80px"] {

                position: relative;

                top: 0;

            }

        }



        .summary-panel {

            background: linear-gradient(135deg, #667eea, #764ba2);

            color: white;

            padding: 2rem;

            border-radius: 15px;

            margin: 2rem 0;

        }



        .opinion-category {

            background: rgba(255, 255, 255, 0.1);

            padding: 1rem;

            border-radius: 10px;

            margin: 1rem 0;

        }



        .percentage-bar {

            background: rgba(255, 255, 255, 0.2);

            height: 20px;

            border-radius: 10px;

            margin: 0.5rem 0;

            overflow: hidden;

        }



        .percentage-fill {

            background: linear-gradient(45deg, #ff6b6b, #feca57);

            height: 100%;

            border-radius: 10px;

            transition: width 0.3s ease;

        }



        .close-btn {

            float: right;

            font-size: 24px;

            cursor: pointer;

            color: #999;

        }



        .close-btn:hover {

            color: #333;

        }



        @media (max-width: 768px) {

            .nav {

                flex-direction: column;

                gap: 1rem;

            }

            

            .search-container {

                flex-direction: column;

            }

            

            .poll-options {

                flex-direction: column;

                align-items: center;

            }

        }



        .loading {

            text-align: center;

            padding: 2rem;

            color: #667eea;

        }



        .spinner {

            border: 4px solid #f3f3f3;

            border-top: 4px solid #667eea;

            border-radius: 50%;

            width: 40px;

            height: 40px;

            animation: spin 1s linear infinite;

            margin: 0 auto;

        }



        @keyframes spin {

            0% { transform: rotate(0deg); }

            100% { transform: rotate(360deg); }

        }

    </style>

</head>

<body oncontextmenu="return false;">

    <div class="watermark">The Open Journal</div>



    <div class="header">

        <div class="container">

            <nav class="nav">

                <div class="logo">The Open Journal</div>

                <div class="nav-buttons">

                    <button class="btn btn-secondary" onclick="showAuthModal()">Sign In</button>

                    <button class="btn btn-primary" onclick="continueAsGuest()">Guest</button>

                </div>

            </nav>

        </div>

    </div>



    <div class="container">

        <div class="ribbon">

            <div class="search-container">

                <input type="text" class="search-box" placeholder="Search topics or opinions..." id="searchInput">

                <select class="filter-dropdown" id="filterSelect">

                    <option value="all">All Posts</option>

                    <option value="date">By Date</option>

                    <option value="country">By Country</option>

                    <option value="popular">Most Popular</option>

                </select>

                <button class="btn btn-primary" onclick="searchPosts()">Search</button>

                <button class="ai-summary-btn" onclick="showAISummary()">AI Summary</button>

            </div>

        </div>



        <div class="ads">

            <h3>🎯 Premium Advertisement</h3>

            <p>🚀 Launch Your Startup Today! Get 50% OFF on business tools - <strong>Limited Time Offer!</strong></p>

        </div>



        <div class="ads" style="background: linear-gradient(45deg, #00d2ff, #3a7bd5);">

            <h3>💎 Exclusive Deal</h3>

            <p>📚 Learn New Skills Online - 1000+ Courses Available | Use Code: JOURNAL2024</p>

        </div>



        <div class="main-content">

            <div class="topic-header">

                <h1 class="topic-title" id="topicTitle">Should remote work become the new standard?</h1>

                <p>Share your thoughts and read what others think about this topic</p>

            </div>



            <div class="poll-section" id="currentPoll">

                <h2>📊 Current Poll</h2>

                <p>What's your stance on remote work?</p>

                <div class="poll-options">

                    <button class="poll-option" onclick="vote('support')">Strong Support</button>

                    <button class="poll-option" onclick="vote('neutral')">Neutral</button>

                    <button class="poll-option" onclick="vote('against')">Against</button>

                    <button class="poll-option" onclick="skipPoll()">Skip</button>

                </div>

            </div>



            <div class="ads">

                <p>💼 Find Your Dream Remote Job - Apply Now! | Top Companies Hiring</p>

            </div>



            <div class="ads" style="background: linear-gradient(45deg, #ff758c, #ff7eb3);">

                <p>🛍️ Fashion Sale Alert! Up to 70% OFF on trending styles - Shop Now!</p>

            </div>



            <div id="postsContainer">

                <div class="ads" style="background: linear-gradient(45deg, #a18cd1, #fbc2eb); margin: 20px 0;">

                    <p>📖 Audiobook Subscription - Listen to 1000+ books | 30-day free trial!</p>

                </div>



                <div class="ads" style="background: linear-gradient(45deg, #ff9a56, #ffad56); margin: 20px 0;">

                    <p>🏋️ Fitness Equipment Sale - Build Your Home Gym | Free Installation!</p>

                </div>



                <div class="post">

                    <div class="post-header">

                        <div class="author-info">

                            <strong>Alex_Techie</strong>

                            <div class="country-flag">🇺🇸</div>

                            <span>United States</span>

                        </div>

                        <small>2 hours ago</small>

                    </div>

                    <div class="post-content">

                        Remote work has completely transformed my productivity. I can focus better without office distractions, and my work-life balance has improved dramatically. Companies that don't adapt to this will lose top talent.

                    </div>

                </div>



                <div class="post">

                    <div class="post-header">

                        <div class="author-info">

                            <strong>Maria_Barcelona</strong>

                            <div class="country-flag">🇪🇸</div>

                            <span>Spain</span>

                        </div>

                        <small>4 hours ago</small>

                    </div>

                    <div class="post-content">

                        While remote work has benefits, I miss the collaborative energy of being in an office. Some tasks just work better when you can have impromptu discussions with colleagues. A hybrid model might be the sweet spot.

                    </div>

                </div>



                <div class="post">

                    <div class="post-header">

                        <div class="author-info">

                            <strong>TechStartupGuy</strong>

                            <div class="country-flag">🇮🇳</div>

                            <span>India</span>

                        </div>

                        <small>6 hours ago</small>

                    </div>

                    <div class="post-content">

                        From a business perspective, remote work reduces overhead costs significantly. We've saved thousands on office rent and utilities. Our team is more global now, and we can hire the best talent regardless of location.

                    </div>

                </div>

            </div>



            <div class="ads">

                <p>🏠 Best Home Office Equipment - Special Discount Available!</p>

            </div>



            <div class="ads" style="background: linear-gradient(45degree, #a8edea, #fed6e3);">

                <p>🎮 Gaming Paradise: Latest Games & Accessories | Free Shipping Worldwide!</p>

            </div>



            <div class="ads" style="background: linear-gradient(45deg, #ffecd2, #fcb69f);">

                <p>🍕 Food Delivery App - Order Now & Get 30% OFF your first meal!</p>

            </div>

        </div>





    </div>



    <!-- Authentication Modal -->

    <div class="modal" id="authModal">

        <div class="modal-content">

            <span class="close-btn" onclick="closeModal()">&times;</span>

            <h2>Join The Open Journal</h2>

            <div class="auth-options">

                <button class="auth-btn google-btn" onclick="signInWith('google')">🔴 Continue with Google</button>

                <button class="auth-btn facebook-btn" onclick="signInWith('facebook')">📘 Continue with Facebook</button>

                <button class="auth-btn phone-btn" onclick="signInWith('phone')">📱 Continue with Phone</button>

                <button class="auth-btn email-btn" onclick="signInWith('email')">📧 Continue with Email</button>

                <button class="auth-btn guest-btn" onclick="continueAsGuest()">👤 Continue as Guest</button>

            </div>

        </div>

    </div>



    <!-- Guest Registration Modal -->

    <div class="modal" id="guestModal">

        <div class="modal-content">

            <span class="close-btn" onclick="closeModal()">&times;</span>

            <h2>Guest Registration</h2>

            <form onsubmit="registerGuest(event)">

                <input type="text" placeholder="Choose a username" required style="width: 100%; padding: 10px; margin: 10px 0; border: 1px solid #ddd; border-radius: 5px;">

                <select required style="width: 100%; padding: 10px; margin: 10px 0; border: 1px solid #ddd; border-radius: 5px;">

                    <option value="">Select your country</option>

                    <option value="US">United States</option>

                    <option value="IN">India</option>

                    <option value="UK">United Kingdom</option>

                    <option value="CA">Canada</option>

                    <option value="AU">Australia</option>

                    <option value="DE">Germany</option>

                    <option value="FR">France</option>

                    <option value="JP">Japan</option>

                    <option value="BR">Brazil</option>

                    <option value="ES">Spain</option>

                </select>

                <button type="submit" class="btn btn-primary" style="width: 100%; margin-top: 10px;">Continue</button>

            </form>

        </div>

    </div>



    <!-- AI Summary Modal -->

    <div class="modal" id="summaryModal">

        <div class="modal-content" style="max-width: 800px;">

            <span class="close-btn" onclick="closeModal()">&times;</span>

            <div class="summary-panel">

                <h2>🤖 AI Summary & Analysis</h2>

                <div class="loading" id="summaryLoading">

                    <div class="spinner"></div>

                    <p>Analyzing all opinions...</p>

                </div>

                <div id="summaryContent" style="display: none;">

                    <div class="opinion-category">

                        <h3>📈 Strong Support (45%)</h3>

                        <div class="percentage-bar">

                            <div class="percentage-fill" style="width: 45%;"></div>

                        </div>

                        <p>Users emphasize increased productivity, better work-life balance, and cost savings.</p>

                    </div>

                    <div class="opinion-category">

                        <h3>⚖️ Neutral/Hybrid Approach (35%)</h3>

                        <div class="percentage-bar">

                            <div class="percentage-fill" style="width: 35%;"></div>

                        </div>

                        <p>Many prefer a balanced approach combining remote and in-office work.</p>

                    </div>

                    <div class="opinion-category">

                        <h3>❌ Against Remote Work (20%)</h3>

                        <div class="percentage-bar">

                            <div class="percentage-fill" style="width: 20%;"></div>

                        </div>

                        <p>Concerns about collaboration, team building, and company culture.</p>

                    </div>

                    <h3>🎯 Key Insights:</h3>

                    <ul style="text-align: left; margin: 1rem 0;">

                        <li>Remote work satisfaction varies by industry and role</li>

                        <li>Hybrid models are gaining popularity as a compromise</li>

                        <li>Technology and management practices are crucial for success</li>

                    </ul>

                </div>

            </div>

        </div>

    </div>



    <script>

        // Global variables

        let currentUser = null;

        let posts = [];

        let currentTopic = "Should remote work become the new standard?";



        // Disable right-click

        document.addEventListener('contextmenu', function(e) {

            e.preventDefault();

        });



        // Disable text selection

        document.addEventListener('selectstart', function(e) {

            e.preventDefault();

        });



        // Modal functions

        function showAuthModal() {

            document.getElementById('authModal').style.display = 'block';

        }



        function closeModal() {

            document.querySelectorAll('.modal').forEach(modal => {

                modal.style.display = 'none';

            });

        }



        function signInWith(provider) {

            alert(`Signing in with ${provider}... (Demo mode)`);

            currentUser = { name: `User_${provider}`, country: 'US', provider: provider };

            closeModal();

            updateUI();

        }



        function continueAsGuest() {

            closeModal();

            document.getElementById('guestModal').style.display = 'block';

        }



        function registerGuest(event) {

            event.preventDefault();

            const formData = new FormData(event.target);

            const username = event.target.querySelector('input').value;

            const country = event.target.querySelector('select').value;

            

            currentUser = { name: username, country: country, provider: 'guest' };

            closeModal();

            updateUI();

            alert('Welcome to The Open Journal!');

        }



        function updateUI() {

            if (currentUser) {

                document.querySelector('.nav-buttons').innerHTML = `

                    <span>Welcome, ${currentUser.name}!</span>

                    <button class="btn btn-secondary" onclick="logout()">Logout</button>

                `;

            }

        }



        function logout() {

            currentUser = null;

            document.querySelector('.nav-buttons').innerHTML = `

                <button class="btn btn-secondary" onclick="showAuthModal()">Sign In</button>

                <button class="btn btn-primary" onclick="continueAsGuest()">Guest</button>

            `;

        }



        // Search functionality

        function searchPosts() {

            const query = document.getElementById('searchInput').value;

            const filter = document.getElementById('filterSelect').value;

            

            if (query) {

                document.getElementById('topicTitle').textContent = `Search results for: "${query}"`;

                // Simulate search loading

                document.getElementById('postsContainer').innerHTML = '<div class="loading"><div class="spinner"></div><p>Searching posts...</p></div>';

                

                setTimeout(() => {

                    // Simulate search results

                    document.getElementById('postsContainer').innerHTML = `

                        <div class="post">

                            <div class="post-header">

                                <div class="author-info">

                                    <strong>SearchUser</strong>

                                    <div class="country-flag">🇬🇧</div>

                                    <span>United Kingdom</span>

                                </div>

                                <small>1 hour ago</small>

                            </div>

                            <div class="post-content">

                                Found a relevant post about "${query}". This matches your search criteria perfectly and provides valuable insights on the topic.

                            </div>

                        </div>

                    `;

                }, 1500);

            }

        }



        // Poll functionality

        function vote(option) {

            if (!currentUser) {

                showAuthModal();

                return;

            }

            alert(`Thank you for voting "${option}"! Your opinion has been recorded.`);

            document.getElementById('currentPoll').style.display = 'none';

        }



        function skipPoll() {

            document.getElementById('currentPoll').style.display = 'none';

        }



        // AI Summary functionality

        function showAISummary() {

            document.getElementById('summaryModal').style.display = 'block';

            document.getElementById('summaryLoading').style.display = 'block';

            document.getElementById('summaryContent').style.display = 'none';

            

            // Simulate AI processing

            setTimeout(() => {

                document.getElementById('summaryLoading').style.display = 'none';

                document.getElementById('summaryContent').style.display = 'block';

            }, 3000);

        }



        // Auto-show sign-in popup after scrolling

        let scrollTriggered = false;

        window.addEventListener('scroll', function() {

            if (!scrollTriggered && window.scrollY > 500 && !currentUser) {

                scrollTriggered = true;

                setTimeout(() => {

                    showAuthModal();

                }, 1000);

            }

        });



        // Initialize page

        document.addEventListener('DOMContentLoaded', function() {

            // Add some interactive effects

            document.querySelectorAll('.post').forEach(post => {

                post.addEventListener('mouseenter', function() {

                    this.style.transform = 'translateY(-5px)';

                });

                post.addEventListener('mouseleave', function() {

                    this.style.transform = 'translateY(0)';

                });

            });



            // Search on Enter key

            document.getElementById('searchInput').addEventListener('keypress', function(e) {

                if (e.key === 'Enter') {

                    searchPosts();

                }

            });

        });



        // Close modal when clicking outside

        window.addEventListener('click', function(e) {

            if (e.target.classList.contains('modal')) {

                closeModal();

            }

        });

    </script>

</body>

</html>
