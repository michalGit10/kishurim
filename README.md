<!DOCTYPE html>
<html lang="he" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>טיקצאק החלפות | המקום להחליף כרטיסים בקלות</title>
    <!-- שימוש ב-Bootstrap לעיצוב נקי ומהיר -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <!-- פונט Heebo למראה מודרני -->
    <link href="https://fonts.googleapis.com/css2?family=Heebo:wght@300;400;700&display=swap" rel="stylesheet">
    <!-- אייקונים -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">

    <style>
        :root {
            --primary-color: #007bff; /* הצבע הכחול של טיקצאק */
            --secondary-color: #f8f9fa;
            --text-color: #333;
        }

        body {
            font-family: 'Heebo', sans-serif;
            background-color: #f4f6f9;
            color: var(--text-color);
        }

        /* Navbar */
        .navbar {
            background-color: #fff;
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
        }
        .navbar-brand {
            font-weight: 700;
            color: var(--primary-color) !important;
            font-size: 1.5rem;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, var(--primary-color) 0%, #0056b3 100%);
            color: white;
            padding: 60px 0;
            text-align: center;
            border-radius: 0 0 50% 50% / 20px;
        }

        /* Cards */
        .card {
            border: none;
            border-radius: 12px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: transform 0.3s;
        }
        .card:hover {
            transform: translateY(-5px);
        }

        /* Tabs/Forms */
        .nav-pills .nav-link.active {
            background-color: var(--primary-color);
        }
        .nav-link {
            color: var(--text-color);
        }

        /* System Section Styling */
        #system-area {
            display: none; /* מוסתר עד לזיהוי */
            background: white;
            padding: 30px;
            border-radius: 15px;
            border: 2px solid #e9ecef;
            margin-top: 30px;
        }

        .chat-btn {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background-color: #25d366;
            color: white;
            padding: 15px;
            border-radius: 50%;
            font-size: 24px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.2);
            z-index: 1000;
            cursor: pointer;
        }
    </style>
</head>
<body>

    <!-- Header -->
    <nav class="navbar navbar-expand-lg navbar-light">
        <div class="container">
            <a class="navbar-brand" href="#"><i class="fas fa-ticket-alt"></i> טיקצאק החלפות</a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav me-auto">
                    <li class="nav-item"><a class="nav-link" href="#board">לוח החלפות</a></li>
                    <li class="nav-item"><a class="nav-link" href="#exchange-engine">ביצוע החלפה</a></li>
                </ul>
            </div>
        </div>
    </nav>

    <!-- Hero -->
    <section class="hero">
        <div class="container">
            <h1>נתקעתם עם כרטיס? רוצים לשדרג?</h1>
            <p class="lead">המערכת הרשמית להחלפת כרטיסי טיקצאק בצורה מאובטחת ומהירה.</p>
            <a href="#exchange-engine" class="btn btn-light btn-lg mt-3 fw-bold text-primary">התחל החלפה כעת</a>
        </div>
    </section>

    <div class="container my-5">
        <div class="row">
            
            <!-- צד ימין: לוח מודעות / השארת פרטים -->
            <div class="col-md-5 mb-4" id="board">
                <div class="card p-4 h-100">
                    <h3 class="mb-4 text-primary"><i class="fas fa-bullhorn"></i> פרסם כרטיס להחלפה</h3>
                    <p class="text-muted small">מלא את הפרטים כדי למצוא שותף להחלפה. ניתן לפתוח צ'אט ישיר.</p>
                    
                    <form id="postForm">
                        <div class="mb-3">
                            <label class="form-label">שם האירוע</label>
                            <input type="text" class="form-control" placeholder="לדוגמה: ישי ריבו בקיסריה">
                        </div>
                        <div class="row">
                            <div class="col-6 mb-3">
                                <label class="form-label">סוג כרטיס</label>
                                <select class="form-select">
                                    <option>רגיל</option>
                                    <option>VIP</option>
                                    <option>סטודנט</option>
                                </select>
                            </div>
                            <div class="col-6 mb-3">
                                <label class="form-label">מגדר (לאירוע נפרד)</label>
                                <select class="form-select">
                                    <option>ללא</option>
                                    <option>גברים</option>
                                    <option>נשים</option>
                                </select>
                            </div>
                        </div>
                        <div class="mb-3">
                            <label class="form-label">מיקום (אולם/יציע)</label>
                            <input type="text" class="form-control" placeholder="יציע ג', שורה 5">
                        </div>
                        <div class="mb-3">
                            <label class="form-label">כתובת מייל</label>
                            <input type="email" class="form-control" placeholder="your@email.com">
                        </div>
                        <button type="button" class="btn btn-outline-primary w-100" onclick="alert('המודעה פורסמה בהצלחה בלוח המודעות!')">
                            פרסם מודעה
                        </button>
                    </form>
                    
                    <hr>
                    <div class="mt-3">
                        <h6>מודעות אחרונות:</h6>
                        <div class="list-group">
                            <a href="#" class="list-group-item list-group-item-action d-flex justify-content-between align-items-center">
                                <div>
                                    <strong>אברהם פריד - ארנה</strong><br>
                                    <small>יציע 2, גברים - ישראל ישראלי</small>
                                </div>
                                <button class="btn btn-sm btn-success rounded-circle"><i class="fas fa-comments"></i></button>
                            </a>
                        </div>
                    </div>
                </div>
            </div>

            <!-- צד שמאל: מנוע ההחלפות (הקוד) -->
            <div class="col-md-7" id="exchange-engine">
                <div class="card p-4 bg-white">
                    <h2 class="text-center mb-4 text-primary">מערכת ביצוע החלפות</h2>

                    <!-- שלב 1: זיהוי -->
                    <div id="step-login">
                        <div class="alert alert-info">
                            <i class="fas fa-lock"></i> אנא הזדהה באמצעות פרטי הכרטיס הקיים ברשותך
                        </div>
                        <div class="mb-3">
                            <label class="form-label">שם בעל הכרטיס (כפי שמופיע בהזמנה)</label>
                            <input type="text" id="loginName" class="form-control" placeholder="לדוגמה: משה כהן">
                        </div>
                        <div class="mb-3">
                            <label class="form-label">קוד כרטיס (ברקוד)</label>
                            <input type="text" id="loginCode" class="form-control" placeholder="לדוגמה: 123456">
                        </div>
                        <button class="btn btn-primary w-100" onclick="verifyUser()">המשך למערכת</button>
                        <p id="loginError" class="text-danger mt-2 text-center" style="display:none;">פרטים שגויים, נסה שוב (נסה: משה כהן, 123456)</p>
                    </div>

                    <!-- שלב 2: תפריט ראשי -->
                    <div id="step-menu" style="display:none;">
                        <h5 id="welcomeMsg" class="text-center mb-4"></h5>
                        <div class="d-grid gap-3">
                            <button class="btn btn-outline-primary btn-lg p-4" onclick="showExchangeType('p2p')">
                                <i class="fas fa-users fa-2x mb-2"></i><br>
                                החלפה בין 2 משתמשים
                                <small class="d-block text-muted">החלפת כרטיסים עם חבר או אדם שמצאת</small>
                            </button>
                            <button class="btn btn-outline-dark btn-lg p-4" onclick="showExchangeType('system')">
                                <i class="fas fa-sync-alt fa-2x mb-2"></i><br>
                                החלפה מול המערכת
                                <small class="d-block text-muted">החלף למושב אחר או תאריך אחר באותה הפקה</small>
                            </button>
                        </div>
                    </div>

                    <!-- שלב 3א: החלפה בין משתמשים -->
                    <div id="step-p2p" style="display:none;">
                        <button class="btn btn-sm btn-link mb-3" onclick="backToMenu()">חזרה לתפריט</button>
                        <h4>החלפה בין משתמשים</h4>
                        <p class="small text-muted">המערכת תאמת את שני הכרטיסים ותבצע החלפת בעלות.</p>
                        
                        <div class="card bg-light p-3 mb-3">
                            <h6>פרטי הפרטנר להחלפה:</h6>
                            <div class="mb-2">
                                <input type="text" id="p2pEventCode" class="form-control" placeholder="קוד אירוע">
                            </div>
                            <div class="mb-2">
                                <input type="text" id="p2pTicketCode" class="form-control" placeholder="קוד כרטיס של הפרטנר">
                            </div>
                             <div class="mb-2">
                                <input type="text" id="p2pName" class="form-control" placeholder="שם בעל הכרטיס השני">
                            </div>
                        </div>
                        <button class="btn btn-success w-100" onclick="executeP2PExchange()">בצע החלפה ושליחת כרטיסים למייל</button>
                    </div>

                    <!-- שלב 3ב: החלפה מול המערכת -->
                    <div id="step-system" style="display:none;">
                        <button class="btn btn-sm btn-link mb-3" onclick="backToMenu()">חזרה לתפריט</button>
                        <h4>החלפה מול המערכת</h4>
                        <div class="mb-3">
                            <label>בחר אירוע אחר (באותה הפקה)</label>
                            <select class="form-select mb-2" id="newSystemEvent">
                                <option value="evt1">אותו אירוע - שינוי מושב</option>
                                <option value="evt2">תאריך חלופי - 20/12/2025</option>
                            </select>
                        </div>
                        <div class="mb-3">
                            <label>בחר מושב חדש פנוי</label>
                            <select class="form-select" id="newSystemSeat">
                                <option value="A1">שורה 1, כיסא 5 (תוספת 0 ₪)</option>
                                <option value="A2">שורה 10, כיסא 12 (זיכוי 20 ₪)</option>
                            </select>
                        </div>
                        <button class="btn btn-primary w-100" onclick="executeSystemExchange()">אשר שינוי ושלח כרטיס חדש</button>
                    </div>

                    <!-- מסך הצלחה -->
                    <div id="step-success" style="display:none;" class="text-center">
                        <div class="text-success mb-3">
                            <i class="fas fa-check-circle fa-5x"></i>
                        </div>
                        <h3>ההחלפה בוצעה בהצלחה!</h3>
                        <p>הכרטיסים הישנים בוטלו.</p>
                        <p><strong>הכרטיסים החדשים נשלחו לכתובות המייל של המזמינים המעודכנים.</strong></p>
                        <button class="btn btn-primary mt-3" onclick="location.reload()">חזרה לדף הבית</button>
                    </div>

                </div>
            </div>
        </div>
    </div>

    <!-- כפתור צ'אט -->
    <div class="chat-btn" onclick="openChat()">
        <i class="fab fa-whatsapp"></i>
    </div>

    <!-- Scripts -->
    <script>
        // --- Mock Database (סימולציה של מסד נתונים) ---
        const db = {
            tickets: [
                { code: "123456", name: "משה כהן", eventId: "EVT001", seat: "שורה 5 כסא 2", email: "moshe@test.com", status: "valid" },
                { code: "654321", name: "דוד לוי", eventId: "EVT001", seat: "שורה 20 כסא 8", email: "david@test.com", status: "valid" },
                { code: "999999", name: "ישראל ישראלי", eventId: "EVT002", seat: "VIP", email: "israel@test.com", status: "valid" }
            ]
        };

        let currentUser = null;

        // --- פונקציית זיהוי ---
        function verifyUser() {
            const nameInput = document.getElementById('loginName').value;
            const codeInput = document.getElementById('loginCode').value;
            const errorMsg = document.getElementById('loginError');

            // בדיקה מול ה-"DB"
            const user = db.tickets.find(t => t.code === codeInput && t.name === nameInput);

            if (user) {
                currentUser = user;
                errorMsg.style.display = 'none';
                document.getElementById('step-login').style.display = 'none';
                document.getElementById('step-menu').style.display = 'block';
                document.getElementById('welcomeMsg').innerText = `שלום, ${currentUser.name} (כרטיס: ${currentUser.code})`;
            } else {
                errorMsg.style.display = 'block';
            }
        }

        // --- ניווט בין מסכים ---
        function showExchangeType(type) {
            document.getElementById('step-menu').style.display = 'none';
            if (type === 'p2p') {
                document.getElementById('step-p2p').style.display = 'block';
            } else {
                document.getElementById('step-system').style.display = 'block';
            }
        }

        function backToMenu() {
            document.getElementById('step-p2p').style.display = 'none';
            document.getElementById('step-system').style.display = 'none';
            document.getElementById('step-menu').style.display = 'block';
        }

        // --- אופציה 1: החלפה בין משתמשים ---
        function executeP2PExchange() {
            const partnerCode = document.getElementById('p2pTicketCode').value;
            const partnerName = document.getElementById('p2pName').value;
            // קוד אירוע לא באמת נבדק בסימולציה אבל נדרש בקלט
            
            // בדיקת תקינות פרטנר
            const partner = db.tickets.find(t => t.code === partnerCode && t.name === partnerName);

            if (!partner) {
                alert('פרטי הפרטנר שגויים או שהכרטיס אינו קיים במערכת');
                return;
            }

            if (partner.code === currentUser.code) {
                alert('לא ניתן להחליף עם עצמך...');
                return;
            }

            // סימולציית ההחלפה (Backend Logic)
            const tempSeat = currentUser.seat;
            currentUser.seat = partner.seat;
            partner.seat = tempSeat;

            // עדכון שמות (אופציונלי - תלוי בלוגיקה העסקית, כאן אנחנו רק מחליפים בעלות)
            // בפועל המערכת מייצרת כרטיס חדש ושולחת במייל
            
            console.log(`Email sent to ${currentUser.email}: New Seat ${currentUser.seat}`);
            console.log(`Email sent to ${partner.email}: New Seat ${partner.seat}`);

            finishProcess();
        }

        // --- אופציה 2: החלפה מול מערכת ---
        function executeSystemExchange() {
            const newSeat = document.getElementById('newSystemSeat').value;
            
            // עדכון המשתמש
            currentUser.seat = newSeat;
            
            console.log(`Email sent to ${currentUser.email}: System Exchange to ${newSeat}`);
            
            finishProcess();
        }

        function finishProcess() {
            document.getElementById('step-p2p').style.display = 'none';
            document.getElementById('step-system').style.display = 'none';
            document.getElementById('step-success').style.display = 'block';
        }

        // --- צאט ---
        function openChat() {
            const phone = "972500000000"; // מספר הוואטסאפ של העסק
            const text = "היי, אשמח לעזרה בנוגע להחלפת כרטיס בטיקצאק";
            window.open(`https://wa.me/${phone}?text=${encodeURIComponent(text)}`, '_blank');
        }

    </script>
</body>
</html>
