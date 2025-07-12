
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BNG Agency - For The Mind By Heart</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-black: #000000;
            --primary-white: #ffffff;
            --primary-blue: #007bff;
            --accent-blue: #4d94ff;
            --light-blue: #e8f2ff;
            --text-gray: #333333;
            --light-gray: #f8f9fa;
            --border-gray: #e0e0e0;
            --orange: #ff6b35;
            --purple: #8e24aa;
            --green: #00c853;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
            line-height: 1.6;
            color: var(--text-gray);
            overflow-x: hidden;
            background: var(--primary-white);
        }

        /* Navigation */
        nav {
            position: fixed;
            width: 100%;
            top: 0;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(20px);
            box-shadow: 0 2px 20px rgba(0, 0, 0, 0.1);
            z-index: 1000;
            transition: all 0.3s ease;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 15px 30px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
            text-decoration: none;
            color: var(--primary-black);
            cursor: pointer;
        }

        .logo-icon {
            width: 45px;
            height: 45px;
            border: 2px solid var(--primary-black);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            font-weight: bold;
            font-style: italic;
            transition: all 0.3s ease;
            border-radius: 8px;
        }

        .logo:hover .logo-icon {
            background: var(--primary-blue);
            border-color: var(--primary-blue);
            color: var(--primary-white);
        }

        .logo-text h1 {
            font-size: 20px;
            font-weight: 900;
            letter-spacing: 1px;
        }

        .logo-text h1 span {
            color: var(--primary-blue);
        }

        .logo-text p {
            font-size: 10px;
            letter-spacing: 1px;
            margin-top: 2px;
            color: var(--text-gray);
            font-weight: 500;
        }

        .nav-menu {
            display: flex;
            gap: 30px;
            list-style: none;
            align-items: center;
        }

        .nav-menu a {
            text-decoration: none;
            color: var(--text-gray);
            font-size: 14px;
            font-weight: 600;
            letter-spacing: 0.5px;
            transition: all 0.3s ease;
            position: relative;
            cursor: pointer;
            padding: 10px 0;
        }

        .nav-menu a.active,
        .nav-menu a:hover {
            color: var(--primary-blue);
        }

        .nav-menu a::after {
            content: '';
            position: absolute;
            bottom: 5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary-blue);
            transition: width 0.3s ease;
        }

        .nav-menu a.active::after,
        .nav-menu a:hover::after {
            width: 100%;
        }

        /* Mobile Menu */
        .mobile-menu-toggle {
            display: none;
            flex-direction: column;
            gap: 4px;
            cursor: pointer;
            padding: 10px;
        }

        .mobile-menu-toggle span {
            width: 25px;
            height: 3px;
            background: var(--primary-black);
            transition: all 0.3s ease;
            border-radius: 2px;
        }

        /* Section visibility */
        .page-section {
            display: block;
        }

        .page-section.hidden {
            display: none;
        }

        /* HOME SECTION */
        #home {
            min-height: 100vh;
            background: linear-gradient(135deg, #ffffff 0%, #f8f9ff 100%);
        }

        .hero-section {
            padding: 120px 30px 80px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .hero-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
            margin-bottom: 80px;
        }

        .hero-text {
            animation: slideInLeft 1s ease-out;
        }

        @keyframes slideInLeft {
            from {
                opacity: 0;
                transform: translateX(-30px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes slideInRight {
            from {
                opacity: 0;
                transform: translateX(30px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .hero-title {
            font-size: clamp(2.5rem, 5vw, 4rem);
            font-weight: 900;
            letter-spacing: -1px;
            margin-bottom: 15px;
            line-height: 1.1;
            color: var(--primary-black);
        }

        .hero-title span {
            color: var(--primary-blue);
        }

        .hero-subtitle {
            font-size: 1.4rem;
            font-weight: 300;
            margin-bottom: 20px;
            color: var(--text-gray);
        }

        .hero-description {
            font-size: 1.1rem;
            line-height: 1.7;
            margin-bottom: 30px;
            color: var(--text-gray);
        }

        .cta-buttons {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
        }

        .cta-button {
            display: inline-block;
            padding: 12px 30px;
            background: var(--primary-blue);
            color: var(--primary-white);
            text-decoration: none;
            font-weight: 600;
            font-size: 14px;
            letter-spacing: 0.5px;
            transition: all 0.3s ease;
            border: 2px solid var(--primary-blue);
            cursor: pointer;
            border-radius: 6px;
        }

        .cta-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(0, 123, 255, 0.3);
        }

        .cta-button-outline {
            background: transparent;
            color: var(--primary-blue);
        }

        .cta-button-outline:hover {
            background: var(--primary-blue);
            color: var(--primary-white);
        }

        .hero-visual {
            position: relative;
            animation: slideInRight 1s ease-out;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
            transform: rotate(2deg);
            perspective: 1000px;
        }

        .service-card {
            aspect-ratio: 1;
            position: relative;
            overflow: hidden;
            transition: all 0.4s ease;
            cursor: pointer;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            transform-style: preserve-3d;
        }

        .service-card:nth-child(1) {
            background: linear-gradient(135deg, #ff6b35, #f7931e);
        }

        .service-card:nth-child(2) {
            background: linear-gradient(135deg, #007bff, #4d94ff);
            transform: translateY(15px);
        }

        .service-card:nth-child(3) {
            background: linear-gradient(135deg, #8e24aa, #5e35b1);
            transform: translateY(-15px);
        }

        .service-card:nth-child(4) {
            background: linear-gradient(135deg, #00c853, #64dd17);
        }

        .service-card:hover {
            transform: scale(1.05) rotate(-2deg) translateZ(20px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
            z-index: 10;
        }

        .service-card-content {
            position: absolute;
            inset: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            color: var(--primary-white);
            text-align: center;
            padding: 20px;
            background: rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }

        .service-card:hover .service-card-content {
            background: rgba(0, 0, 0, 0.3);
        }

        .service-icon {
            font-size: 2.5rem;
            margin-bottom: 15px;
            filter: drop-shadow(0 2px 4px rgba(0,0,0,0.3));
        }

        .service-title {
            font-size: 1.1rem;
            font-weight: 800;
            text-transform: uppercase;
            letter-spacing: 1px;
            text-shadow: 0 2px 4px rgba(0,0,0,0.5);
            margin-bottom: 8px;
        }

        .service-hint {
            font-size: 0.8rem;
            opacity: 0;
            transform: translateY(10px);
            transition: all 0.3s ease;
        }

        .service-card:hover .service-hint {
            opacity: 1;
            transform: translateY(0);
        }

        /* Stats Section */
        .stats-section {
            background: var(--primary-black);
            color: var(--primary-white);
            padding: 60px 30px;
        }

        .stats-container {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            text-align: center;
        }

        .stat-item {
            padding: 20px;
        }

        .stat-number {
            font-size: 3rem;
            font-weight: 900;
            color: var(--primary-blue);
            margin-bottom: 10px;
            line-height: 1;
        }

        .stat-label {
            font-size: 1rem;
            letter-spacing: 0.5px;
            text-transform: uppercase;
            font-weight: 600;
        }

        /* Mission Section */
        .mission-section {
            padding: 80px 30px;
            background: var(--light-gray);
        }

        .mission-container {
            max-width: 1000px;
            margin: 0 auto;
            text-align: center;
        }

        .section-title {
            font-size: 2.5rem;
            font-weight: 900;
            margin-bottom: 20px;
            color: var(--primary-black);
        }

        .section-description {
            font-size: 1.2rem;
            line-height: 1.7;
            color: var(--text-gray);
            max-width: 800px;
            margin: 0 auto 50px;
        }

        .values-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
            margin-top: 50px;
        }

        .value-card {
            background: var(--primary-white);
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
            border: 1px solid var(--border-gray);
        }

        .value-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(0, 123, 255, 0.15);
        }

        .value-icon {
            font-size: 2.5rem;
            margin-bottom: 20px;
        }

        .value-title {
            font-size: 1.3rem;
            font-weight: 800;
            margin-bottom: 15px;
            color: var(--primary-blue);
        }

        .value-description {
            color: var(--text-gray);
            line-height: 1.6;
        }

        /* SERVIZI SECTION */
        #servizi {
            padding: 100px 30px;
            background: var(--light-gray);
        }

        .services-container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .service-detail {
            background: var(--primary-white);
            margin-bottom: 50px;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
            border: 1px solid var(--border-gray);
        }

        .service-detail:hover {
            transform: translateY(-5px);
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.15);
        }

        .service-header {
            padding: 40px 30px;
            text-align: center;
            position: relative;
        }

        .service-header.brand-activation {
            background: linear-gradient(135deg, #ff6b35, #f7931e);
            color: white;
        }

        .service-header.marketing {
            background: linear-gradient(135deg, #007bff, #4d94ff);
            color: white;
        }

        .service-header.events {
            background: linear-gradient(135deg, #8e24aa, #5e35b1);
            color: white;
        }

        .service-header.ecommerce {
            background: linear-gradient(135deg, #00c853, #64dd17);
            color: white;
        }

        .service-header.photography {
            background: linear-gradient(135deg, #9c27b0, #e91e63);
            color: white;
        }

        .service-number {
            font-size: 1rem;
            font-weight: 600;
            margin-bottom: 10px;
            opacity: 0.8;
        }

        .service-name {
            font-size: 2.2rem;
            font-weight: 900;
            margin-bottom: 15px;
            text-transform: uppercase;
        }

        .service-tagline {
            font-size: 1.1rem;
            opacity: 0.9;
            max-width: 500px;
            margin: 0 auto;
        }

        .service-body {
            padding: 40px 30px;
        }

        .service-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            align-items: start;
        }

        .service-info h3 {
            font-size: 1.5rem;
            font-weight: 800;
            margin-bottom: 20px;
            color: var(--primary-blue);
        }

        .service-features {
            list-style: none;
            margin-bottom: 30px;
        }

        .service-features li {
            padding: 10px 0;
            padding-left: 25px;
            position: relative;
            font-size: 1rem;
            border-bottom: 1px solid var(--border-gray);
            color: var(--text-gray);
        }

        .service-features li:last-child {
            border-bottom: none;
        }

        .service-features li::before {
            content: '✓';
            position: absolute;
            left: 0;
            color: var(--primary-blue);
            font-weight: bold;
        }

        .service-examples {
            background: var(--light-gray);
            padding: 25px;
            border-radius: 10px;
        }

        .service-examples h4 {
            font-size: 1.2rem;
            font-weight: 700;
            margin-bottom: 15px;
            color: var(--primary-blue);
        }

        .example-links {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .example-link {
            display: inline-block;
            padding: 10px 20px;
            background: var(--primary-blue);
            color: var(--primary-white);
            text-decoration: none;
            border-radius: 6px;
            font-weight: 600;
            font-size: 14px;
            transition: all 0.3s ease;
            text-align: center;
        }

        .example-link:hover {
            background: var(--primary-black);
            transform: translateY(-1px);
        }

        .service-visual {
            text-align: center;
            padding: 20px;
        }

        .service-icon-large {
            font-size: 4rem;
            margin-bottom: 20px;
            color: var(--primary-blue);
            filter: drop-shadow(0 5px 15px rgba(0, 123, 255, 0.3));
        }

        .service-visual p {
            color: var(--text-gray);
            line-height: 1.6;
            font-style: italic;
        }

        /* PORTFOLIO SECTION */
        #portfolio {
            padding: 100px 30px;
            background: var(--primary-white);
        }

        .portfolio-container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .portfolio-filters {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-bottom: 50px;
            flex-wrap: wrap;
        }

        .portfolio-filter {
            padding: 10px 20px;
            background: var(--light-gray);
            border: 2px solid var(--border-gray);
            cursor: pointer;
            font-weight: 600;
            font-size: 14px;
            letter-spacing: 0.5px;
            transition: all 0.3s ease;
            text-transform: uppercase;
            border-radius: 6px;
            color: var(--text-gray);
        }

        .portfolio-filter:hover,
        .portfolio-filter.active {
            background: var(--primary-blue);
            color: var(--primary-white);
            border-color: var(--primary-blue);
            transform: translateY(-2px);
        }

        .portfolio-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
        }

        .portfolio-item {
            background: var(--primary-white);
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
            border: 1px solid var(--border-gray);
            cursor: pointer;
        }

        .portfolio-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
        }

        .portfolio-image {
            width: 100%;
            height: 200px;
            position: relative;
            overflow: hidden;
        }

        .portfolio-image.brand-activation {
            background: linear-gradient(135deg, #ff6b35, #f7931e);
        }

        .portfolio-image.marketing {
            background: linear-gradient(135deg, #007bff, #4d94ff);
        }

        .portfolio-image.events {
            background: linear-gradient(135deg, #8e24aa, #5e35b1);
        }

        .portfolio-image.ecommerce {
            background: linear-gradient(135deg, #00c853, #64dd17);
        }

        .portfolio-image.photography {
            background: linear-gradient(135deg, #9c27b0, #e91e63);
        }

        .portfolio-overlay {
            position: absolute;
            inset: 0;
            background: rgba(0, 0, 0, 0.7);
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            transition: all 0.3s ease;
        }

        .portfolio-item:hover .portfolio-overlay {
            opacity: 1;
        }

        .portfolio-play {
            width: 60px;
            height: 60px;
            background: rgba(255, 255, 255, 0.9);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            color: var(--primary-blue);
            transition: all 0.3s ease;
        }

        .portfolio-play:hover {
            transform: scale(1.1);
            background: var(--primary-white);
        }

        .portfolio-content {
            padding: 25px;
        }

        .portfolio-category {
            font-size: 0.8rem;
            font-weight: 600;
            color: var(--primary-blue);
            text-transform: uppercase;
            letter-spacing: 0.5px;
            margin-bottom: 8px;
        }

        .portfolio-title {
            font-size: 1.3rem;
            font-weight: 800;
            margin-bottom: 10px;
            color: var(--primary-black);
        }

        .portfolio-description {
            color: var(--text-gray);
            margin-bottom: 15px;
            line-height: 1.5;
            font-size: 0.95rem;
        }

        .portfolio-link {
            display: inline-block;
            padding: 8px 20px;
            background: var(--primary-blue);
            color: var(--primary-white);
            text-decoration: none;
            font-weight: 600;
            font-size: 13px;
            border-radius: 5px;
            transition: all 0.3s ease;
        }

        .portfolio-link:hover {
            background: var(--primary-black);
            transform: translateY(-1px);
        }

        /* CONTATTI SECTION */
        #contatti {
            padding: 100px 30px;
            background: var(--light-gray);
        }

        .contact-container {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: start;
        }

        .contact-info h3 {
            font-size: 2rem;
            font-weight: 800;
            margin-bottom: 30px;
            text-transform: uppercase;
            color: var(--primary-blue);
        }

        .contact-details {
            display: flex;
            flex-direction: column;
            gap: 25px;
        }

        .contact-item {
            display: flex;
            align-items: flex-start;
            gap: 20px;
            background: var(--primary-white);
            padding: 25px;
            border-radius: 12px;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
            border: 1px solid var(--border-gray);
        }

        .contact-item:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 35px rgba(0, 123, 255, 0.15);
        }

        .contact-icon {
            width: 50px;
            height: 50px;
            background: var(--primary-blue);
            color: var(--primary-white);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            border-radius: 8px;
            flex-shrink: 0;
        }

        .contact-text h4 {
            font-weight: 700;
            margin-bottom: 8px;
            text-transform: uppercase;
            font-size: 0.9rem;
            letter-spacing: 0.5px;
            color: var(--primary-blue);
        }

        .contact-text p {
            color: var(--text-gray);
            margin-bottom: 3px;
            font-size: 0.95rem;
        }

        .contact-text a {
            color: var(--primary-blue);
            text-decoration: none;
            transition: all 0.3s ease;
            font-weight: 600;
        }

        .contact-text a:hover {
            text-decoration: underline;
        }

        .contact-form {
            background: var(--primary-white);
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
            border: 1px solid var(--border-gray);
        }

        .form-header {
            text-align: center;
            margin-bottom: 30px;
        }

        .form-header h3 {
            font-size: 1.8rem;
            font-weight: 800;
            margin-bottom: 8px;
            color: var(--primary-blue);
        }

        .form-header p {
            color: var(--text-gray);
            font-size: 1rem;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 6px;
            font-weight: 700;
            letter-spacing: 0.5px;
            text-transform: uppercase;
            font-size: 0.8rem;
            color: var(--primary-blue);
        }

        .form-group input,
        .form-group select,
        .form-group textarea {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid var(--border-gray);
            background: var(--primary-white);
            font-family: inherit;
            font-size: 15px;
            transition: all 0.3s ease;
            border-radius: 6px;
        }

        .form-group input:focus,
        .form-group select:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--primary-blue);
            box-shadow: 0 0 0 3px rgba(0, 123, 255, 0.1);
        }

        .submit-button {
            width: 100%;
            padding: 15px 30px;
            background: var(--primary-blue);
            color: var(--primary-white);
            border: none;
            font-weight: 700;
            letter-spacing: 0.5px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 15px;
            text-transform: uppercase;
            border-radius: 6px;
        }

        .submit-button:hover {
            background: var(--primary-black);
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2);
        }

        .success-message {
            background: #4CAF50;
            color: white;
            padding: 15px;
            border-radius: 6px;
            margin-bottom: 20px;
            display: none;
            font-weight: 600;
        }

        /* Footer */
        footer {
            background: var(--primary-black);
            color: var(--primary-white);
            padding: 50px 30px 30px;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 2fr 1fr 1fr;
            gap: 40px;
            margin-bottom: 30px;
        }

        .footer-brand h3 {
            font-size: 1.8rem;
            font-weight: 900;
            margin-bottom: 15px;
        }

        .footer-brand h3 span {
            color: var(--primary-blue);
        }

        .footer-brand p {
            color: rgba(255, 255, 255, 0.7);
            line-height: 1.6;
            margin-bottom: 20px;
        }

        .social-links {
            display: flex;
            gap: 12px;
        }

        .social-link {
            width: 35px;
            height: 35px;
            background: var(--primary-blue);
            display: flex;
            align-items: center;
            justify-content: center;
            text-decoration: none;
            color: var(--primary-white);
            transition: all 0.3s ease;
            border-radius: 5px;
            font-size: 1.1rem;
        }

        .social-link:hover {
            background: var(--primary-white);
            color: var(--primary-blue);
            transform: translateY(-2px);
        }

        .footer-column h4 {
            font-size: 1.1rem;
            font-weight: 700;
            margin-bottom: 15px;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        .footer-column ul {
            list-style: none;
        }

        .footer-column li {
            margin-bottom: 8px;
        }

        .footer-column a {
            color: rgba(255, 255, 255, 0.7);
            text-decoration: none;
            transition: all 0.3s ease;
            cursor: pointer;
            font-size: 0.95rem;
        }

        .footer-column a:hover {
            color: var(--primary-blue);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: rgba(255, 255, 255, 0.5);
            font-size: 0.9rem;
        }

        /* Responsive Design */
        @media (max-width: 1024px) {
            .hero-content,
            .service-content,
            .contact-container {
                grid-template-columns: 1fr;
                gap: 40px;
            }

            .hero-visual {
                max-width: 400px;
                margin: 0 auto;
            }

            .footer-content {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .social-links {
                justify-content: center;
            }
        }

        @media (max-width: 768px) {
            .nav-menu {
                position: fixed;
                left: -100%;
                top: 70px;
                flex-direction: column;
                background: var(--primary-white);
                width: 100%;
                text-align: center;
                transition: 0.3s;
                box-shadow: 0 10px 27px rgba(0, 0, 0, 0.05);
                padding: 20px 0;
                gap: 15px;
            }

            .nav-menu.active {
                left: 0;
            }

            .mobile-menu-toggle {
                display: flex;
            }

            .hero-title {
                font-size: 2.5rem;
            }

            .stats-container {
                grid-template-columns: repeat(2, 1fr);
            }

            .cta-buttons {
                flex-direction: column;
                align-items: stretch;
            }

            .values-grid,
            .portfolio-grid {
                grid-template-columns: 1fr;
            }

            .portfolio-filters {
                justify-content: flex-start;
                overflow-x: auto;
                padding-bottom: 10px;
            }

            .contact-form {
                padding: 25px;
            }

            .service-header,
            .service-body {
                padding: 30px 20px;
            }

            .services-grid {
                transform: none;
            }

            .service-card:nth-child(2),
            .service-card:nth-child(3) {
                transform: none;
            }
        }

        /* Animation utilities */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .fade-in {
            animation: fadeInUp 0.6s ease-out;
        }

        /* Utility classes */
        .text-center {
            text-align: center;
        }

        .hidden {
            display: none !important;
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav>
        <div class="nav-container">
            <div class="logo" onclick="showPage('home')">
                <div class="logo-icon">B</div>
                <div class="logo-text">
                    <h1>BNG <span>AGENCY</span></h1>
                    <p>FOR THE MIND BY HEART</p>
                </div>
            </div>
            <ul class="nav-menu" id="navMenu">
                <li><a onclick="showPage('home')" id="nav-home" class="active">HOME</a></li>
                <li><a onclick="showPage('servizi')" id="nav-servizi">SERVIZI</a></li>
                <li><a onclick="showPage('portfolio')" id="nav-portfolio">PORTFOLIO</a></li>
                <li><a onclick="showPage('contatti')" id="nav-contatti">CONTATTI</a></li>
            </ul>
            <div class="mobile-menu-toggle" onclick="toggleMobileMenu()">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </div>
    </nav>

    <!-- HOME PAGE -->
    <div id="home" class="page-section">
        <!-- Hero Section -->
        <section class="hero-section">
            <div class="hero-content">
                <div class="hero-text">
                    <h1 class="hero-title">BNG <span>AGENCY</span></h1>
                    <p class="hero-subtitle">For The Mind By Heart</p>
                    <p class="hero-description">
                        Un'agenzia creativa full-service che affianca brand e aziende nel rafforzare la propria presenza mediatica. 
                        Specializzata in attivazioni social con influencer, sviluppa soluzioni personalizzate per aumentare la visibilità online.
                    </p>
                    <div class="cta-buttons">
                        <div onclick="showPage('servizi')" class="cta-button">SCOPRI I SERVIZI</div>
                        <div onclick="showPage('portfolio')" class="cta-button cta-button-outline">VEDI PORTFOLIO</div>
                    </div>
                </div>
                <div class="hero-visual">
                    <div class="services-grid">
                        <div class="service-card" onclick="window.open('https://www.instagram.com/reel/DDo_aFDNjIR/?hl=it', '_blank')">
                            <div class="service-card-content">
                                <div class="service-icon">🎯</div>
                                <div class="service-title">Brand Activation</div>
                                <div class="service-hint">Clicca per vedere un esempio</div>
                            </div>
                        </div>
                        <div class="service-card" onclick="window.open('https://www.instagram.com/p/DAOTO_oNTLx/?hl=it', '_blank')">
                            <div class="service-card-content">
                                <div class="service-icon">📈</div>
                                <div class="service-title">Marketing</div>
                                <div class="service-hint">Clicca per vedere un esempio</div>
                            </div>
                        </div>
                        <div class="service-card" onclick="window.open('https://www.instagram.com/reel/CtGd2FUgkR5/?hl=it', '_blank')">
                            <div class="service-card-content">
                                <div class="service-icon">🎪</div>
                                <div class="service-title">Eventi</div>
                                <div class="service-hint">Clicca per vedere un esempio</div>
                            </div>
                        </div>
                        <div class="service-card" onclick="window.open('https://www.caffe.design/', '_blank')">
                            <div class="service-card-content">
                                <div class="service-icon">💻</div>
                                <div class="service-title">E-commerce</div>
                                <div class="service-hint">Clicca per vedere un esempio</div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Stats Section -->
        <section class="stats-section">
            <div class="stats-container">
                <div class="stat-item">
                    <div class="stat-number">+97</div>
                    <div class="stat-label">Eventi Organizzati</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">+47</div>
                    <div class="stat-label">Brand Activation</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">+22</div>
                    <div class="stat-label">Siti Web Realizzati</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">+39</div>
                    <div class="stat-label">Marketing Strategies</div>
                </div>
            </div>
        </section>

        <!-- Mission Section -->
        <section class="mission-section">
            <div class="mission-container">
                <h2 class="section-title">LA NOSTRA MISSION</h2>
                <p class="section-description">
                    La missione di BNG Agency è supportare le aziende nel raggiungimento dei propri obiettivi strategici 
                    attraverso strategie digitali su misura, attivazioni social, talent management e produzioni creative. 
                    Crediamo in una comunicazione autentica e ad alto impatto, capace di generare valore concreto.
                </p>
                
                <div class="values-grid">
                    <div class="value-card">
                        <div class="value-icon">🧠</div>
                        <h3 class="value-title">Salute Mentale</h3>
                        <p class="value-description">
                            Promuoviamo la salute mentale come elemento centrale del nostro approccio, 
                            offrendo intrattenimento di qualità e collaborazioni con partner selezionati.
                        </p>
                    </div>
                    <div class="value-card">
                        <div class="value-icon">🌱</div>
                        <h3 class="value-title">Territorio</h3>
                        <p class="value-description">
                            Valorizziamo il territorio attraverso sinergie con realtà locali e 
                            innoviamo costantemente nel settore degli eventi.
                        </p>
                    </div>
                    <div class="value-card">
                        <div class="value-icon">♻️</div>
                        <h3 class="value-title">Sostenibilità</h3>
                        <p class="value-description">
                            Operiamo nel pieno rispetto dell'ambiente e dei principi ESG, 
                            promuovendo pratiche sostenibili in ogni nostro progetto.
                        </p>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- SERVIZI PAGE -->
    <div id="servizi" class="page-section hidden">
        <section class="hero-section text-center">
            <h1 class="section-title">I NOSTRI SERVIZI</h1>
            <p class="section-description">Soluzioni complete e personalizzate per rafforzare la presenza mediatica del tuo brand</p>
        </section>

        <div class="services-container">
            <!-- Brand Activation -->
            <div class="service-detail">
                <div class="service-header brand-activation">
                    <div class="service-number">01</div>
                    <h2 class="service-name">Brand Activation</h2>
                    <p class="service-tagline">Creiamo attivazioni social su misura per aumentare visibilità e coinvolgimento</p>
                </div>
                <div class="service-body">
                    <div class="service-content">
                        <div class="service-info">
                            <h3>Cosa facciamo:</h3>
                            <ul class="service-features">
                                <li>Strategie social ad alto impatto per amplificare la visibilità</li>
                                <li>Selezione mirata di influencer e content creator</li>
                                <li>Creazione di contenuti autentici e ingaggianti</li>
                                <li>Focus su visibilità, credibilità e connessione emotiva</li>
                                <li>Campagne personalizzate per ogni target</li>
                            </ul>
                            <div class="service-examples">
                                <h4>Alcuni esempi:</h4>
                                <div class="example-links">
                                    <a href="https://www.instagram.com/reel/DITd0PbtES9/" target="_blank" class="example-link">Campagna Influencer #1</a>
                                    <a href="https://www.instagram.com/p/DIokrLDKZb8/" target="_blank" class="example-link">Content Creation #2</a>
                                    <a href="https://www.instagram.com/p/DH6D_uRNulw/" target="_blank" class="example-link">Brand Partnership #3</a>
                                    <a href="https://www.instagram.com/p/C53e1OpKH1b/" target="_blank" class="example-link">Collaborazione #4</a>
                                    <a href="https://www.instagram.com/p/DK9triMNQmv/?hl=it" target="_blank" class="example-link">Attivazione Social #5</a>
                                </div>
                            </div>
                        </div>
                        <div class="service-visual">
                            <div class="service-icon-large">🎯</div>
                            <p>Con contenuti autentici realizzati da creator selezionati, rafforziamo identità e connessione emotiva con il pubblico.</p>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Marketing Strategies -->
            <div class="service-detail">
                <div class="service-header marketing">
                    <div class="service-number">02</div>
                    <h2 class="service-name">Marketing Strategies</h2>
                    <p class="service-tagline">Sviluppiamo strategie su misura per ottenere risultati concreti e misurabili</p>
                </div>
                <div class="service-body">
                    <div class="service-content">
                        <div class="service-info">
                            <h3>Il nostro approccio:</h3>
                            <ul class="service-features">
                                <li>Approccio integrato: analisi dati + creatività</li>
                                <li>Gestione professionale dei canali social</li>
                                <li>Pianificazione di campagne omnicanale</li>
                                <li>Definizione del posizionamento e del target</li>
                                <li>Azioni mirate per rafforzare identità e visibilità del brand</li>
                            </ul>
                            <div class="service-examples">
                                <h4>Case studies:</h4>
                                <div class="example-links">
                                    <a href="https://www.instagram.com/p/DAOTO_oNTLx/?hl=it" target="_blank" class="example-link">Strategia Digitale Completa</a>
                                    <a href="https://www.instagram.com/valentinaclerici/?hl=it" target="_blank" class="example-link">Gestione Social Media</a>
                                </div>
                            </div>
                        </div>
                        <div class="service-visual">
                            <div class="service-icon-large">📈</div>
                            <p>Unendo creatività e approccio data-driven, rafforziamo la presenza digitale dei brand e ne guidiamo la crescita strategica.</p>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Event Production -->
            <div class="service-detail">
                <div class="service-header events">
                    <div class="service-number">03</div>
                    <h2 class="service-name">Event Production</h2>
                    <p class="service-tagline">Trasformiamo ogni evento in un'esperienza memorabile, curata in ogni dettaglio</p>
                </div>
                <div class="service-body">
                    <div class="service-content">
                        <div class="service-info">
                            <h3>Cosa organizziamo:</h3>
                            <ul class="service-features">
                                <li>Festival, eventi aziendali e feste private</li>
                                <li>Audio/luci, DJ set, catering, allestimenti</li>
                                <li>Regia creativa e attenzione ai dettagli</li>
                                <li>Collaborazione con partner selezionati</li>
                                <li>Focus su innovazione e impatto emotivo</li>
                            </ul>
                            <div class="service-examples">
                                <h4>Eventi realizzati:</h4>
                                <div class="example-links">
                                    <a href="https://www.instagram.com/reel/CtGd2FUgkR5/?hl=it" target="_blank" class="example-link">Festival Musicale</a>
                                    <a href="https://www.instagram.com/p/DLC8VWctIu7/" target="_blank" class="example-link">Evento Corporate</a>
                                    <a href="https://www.instagram.com/p/DAJ-MVqN-HL/" target="_blank" class="example-link">Festa Privata</a>
                                </div>
                            </div>
                        </div>
                        <div class="service-visual">
                            <div class="service-icon-large">🎪</div>
                            <p>Dai festival ai corporate event, offriamo soluzioni complete e personalizzate per esperienze indimenticabili.</p>
                        </div>
                    </div>
                </div>
            </div>

            <!-- E-commerce Development -->
            <div class="service-detail">
                <div class="service-header ecommerce">
                    <div class="service-number">04</div>
                    <h2 class="service-name">Sviluppo E-commerce</h2>
                    <p class="service-tagline">Soluzioni digitali su misura per accelerare la crescita online delle aziende</p>
                </div>
                <div class="service-body">
                    <div class="service-content">
                        <div class="service-info">
                            <h3>Cosa realizziamo:</h3>
                            <ul class="service-features">
                                <li>Design intuitivo e performance tecniche ottimizzate</li>
                                <li>Strategie mirate alla conversione e alla crescita online</li>
                                <li>Focus sull'esperienza utente e sugli obiettivi di business</li>
                                <li>Dal sito vetrina allo shop online completo</li>
                                <li>Studio fotografico professionale incluso</li>
                            </ul>
                            <div class="service-examples">
                                <h4>Progetti realizzati:</h4>
                                <div class="example-links">
                                    <a href="https://www.caffe.design/" target="_blank" class="example-link">Caffe Design - E-commerce</a>
                                    <a href="https://gigaciao.com/" target="_blank" class="example-link">Gigaciao - Marketplace</a>
                                    <a href="https://cophouse.com/" target="_blank" class="example-link">Cophouse - Website</a>
                                    <a href="https://www.milanodascrocco.com/" target="_blank" class="example-link">Milano da Scrocco</a>
                                </div>
                            </div>
                        </div>
                        <div class="service-visual">
                            <div class="service-icon-large">💻</div>
                            <p>Creiamo piattaforme funzionali e moderne che rispecchiano l'identità del brand, dal sito vetrina allo shop online completo.</p>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Photography Studio -->
            <div class="service-detail">
                <div class="service-header photography">
                    <div class="service-number">05</div>
                    <h2 class="service-name">Studio Fotografico</h2>
                    <p class="service-tagline">Pixel Studio - Spazio professionale per produzioni foto e video di alta qualità</p>
                </div>
                <div class="service-body">
                    <div class="service-content">
                        <div class="service-info">
                            <h3>Il nostro studio:</h3>
                            <ul class="service-features">
                                <li>100 mq di superficie con limbo da 4,05 m e altezza di 3,50 m</li>
                                <li>Ambientazione personalizzabile per ogni esigenza creativa</li>
                                <li>Camerino privato e postazione make-up a disposizione</li>
                                <li>Ideale per produzioni editoriali, commerciali e social</li>
                                <li>Attrezzatura professionale completa inclusa</li>
                            </ul>
                            <div class="service-examples">
                                <h4>Servizi inclusi:</h4>
                                <div class="example-links">
                                    <a href="https://drive.google.com/file/d/1CgOha7mgRUxGQaGjUqcUjeBTOTsv2X_W/view?usp=drive_link" target="_blank" class="example-link">Virtual Tour Studio</a>
                                </div>
                            </div>
                        </div>
                        <div class="service-visual">
                            <div class="service-icon-large">📸</div>
                            <p>BNG Agency è proprietaria di Pixel Studio, situato a Milano in Viale Campania 5. Spazio versatile e personalizzabile per ogni tipo di produzione.</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- PORTFOLIO PAGE -->
    <div id="portfolio" class="page-section hidden">
        <section class="hero-section text-center">
            <h1 class="section-title">IL NOSTRO PORTFOLIO</h1>
            <p class="section-description">Scopri i progetti che hanno portato risultati straordinari ai nostri clienti</p>
        </section>

        <div class="portfolio-container">
            <div class="portfolio-filters">
                <button class="portfolio-filter active" onclick="filterPortfolio('all')">TUTTI</button>
                <button class="portfolio-filter" onclick="filterPortfolio('brand')">BRAND ACTIVATION</button>
                <button class="portfolio-filter" onclick="filterPortfolio('marketing')">MARKETING</button>
                <button class="portfolio-filter" onclick="filterPortfolio('events')">EVENTI</button>
                <button class="portfolio-filter" onclick="filterPortfolio('web')">E-COMMERCE</button>
                <button class="portfolio-filter" onclick="filterPortfolio('photography')">FOTOGRAFIA</button>
            </div>
            
            <div class="portfolio-grid">
                <!-- Brand Activation Projects -->
                <div class="portfolio-item" data-category="brand">
                    <div class="portfolio-image brand-activation">
                        <div class="portfolio-overlay">
                            <div class="portfolio-play">▶</div>
                        </div>
                    </div>
                    <div class="portfolio-content">
                        <div class="portfolio-category">Brand Activation</div>
                        <h3 class="portfolio-title">Campagna Influencer - Valentina Clerici</h3>
                        <p class="portfolio-description">Strategia social completa con content creator selezionati per massimizzare engagement e reach organico.</p>
                        <a href="https://www.instagram.com/reel/DITd0PbtES9/" target="_blank" class="portfolio-link">GUARDA VIDEO</a>
                    </div>
                </div>

                <div class="portfolio-item" data-category="brand">
                    <div class="portfolio-image brand-activation">
                        <div class="portfolio-overlay">
                            <div class="portfolio-play">▶</div>
                        </div>
                    </div>
                    <div class="portfolio-content">
                        <div class="portfolio-category">Brand Activation</div>
                        <h3 class="portfolio-title">Content Creation Autentici</h3>
                        <p class="portfolio-description">Produzione di contenuti ingaggianti che rafforzano l'identità del brand e la connessione emotiva.</p>
                        <a href="https://www.instagram.com/p/DIokrLDKZb8/" target="_blank" class="portfolio-link">GUARDA VIDEO</a>
                    </div>
                </div>

                <div class="portfolio-item" data-category="brand">
                    <div class="portfolio-image brand-activation">
                        <div class="portfolio-overlay">
                            <div class="portfolio-play">▶</div>
                        </div>
                    </div>
                    <div class="portfolio-content">
                        <div class="portfolio-category">Brand Activation</div>
                        <h3 class="portfolio-title">Partnership Strategiche</h3>
                        <p class="portfolio-description">Collaborazioni mirate con influencer per amplificare la visibilità e credibilità del brand.</p>
                        <a href="https://www.instagram.com/p/DH6D_uRNulw/" target="_blank" class="portfolio-link">GUARDA VIDEO</a>
                    </div>
                </div>

                <div class="portfolio-item" data-category="brand">
                    <div class="portfolio-image brand-activation">
                        <div class="portfolio-overlay">
                            <div class="portfolio-play">▶</div>
                        </div>
                    </div>
                    <div class="portfolio-content">
                        <div class="portfolio-category">Brand Activation</div>
                        <h3 class="portfolio-title">Attivazione Social Completa</h3>
                        <p class="portfolio-description">Strategia integrata per aumentare visibilità e coinvolgimento attraverso content creator autentici.</p>
                        <a href="https://www.instagram.com/p/C53e1OpKH1b/" target="_blank" class="portfolio-link">GUARDA VIDEO</a>
                    </div>
                </div>

                <div class="portfolio-item" data-category="brand">
                    <div class="portfolio-image brand-activation">
                        <div class="portfolio-overlay">
                            <div class="portfolio-play">▶</div>
                        </div>
                    </div>
                    <div class="portfolio-content">
                        <div class="portfolio-category">Brand Activation</div>
                        <h3 class="portfolio-title">Campagna Multi-Creator</h3>
                        <p class="portfolio-description">Coordinamento di più influencer per amplificare il messaggio del brand su diverse piattaforme.</p>
                        <a href="https://www.instagram.com/p/DK9triMNQmv/?hl=it" target="_blank" class="portfolio-link">GUARDA VIDEO</a>
                    </div>
                </div>

                <!-- Marketing Strategy Projects -->
                <div class="portfolio-item" data-category="marketing">
                    <div class="portfolio-image marketing">
                        <div class="portfolio-overlay">
                            <div class="portfolio-play">📊</div>
                        </div>
                    </div>
                    <div class="portfolio-content">
                        <div class="portfolio-category">Marketing Strategy</div>
                        <h3 class="portfolio-title">Strategia Digitale Completa</h3>
                        <p class="portfolio-description">Approccio data-driven che unisce creatività e analisi per massimizzare ROI e conversioni.</p>
                        <a href="https://www.instagram.com/p/DAOTO_oNTLx/?hl=it" target="_blank" class="portfolio-link">GUARDA CASO</a>
                    </div>
                </div>

                <div class="portfolio-item" data-category="marketing">
                    <div class="portfolio-image marketing">
                        <div class="portfolio-overlay">
                            <div class="portfolio-play">📱</div>
                        </div>
                    </div>
                    <div class="portfolio-content">
                        <div class="portfolio-category">Marketing Strategy</div>
                        <h3 class="portfolio-title">Gestione Social Media</h3>
                        <p class="portfolio-description">Gestione professionale multicanale con contenuti personalizzati e strategia di engagement.</p>
                        <a href="https://www.instagram.com/valentinaclerici/?hl=it" target="_blank" class="portfolio-link">VEDI PROFILO</a>
                    </div>
                </div>

                <!-- Event Production Projects -->
                <div class="portfolio-item" data-category="events">
                    <div class="portfolio-image events">
                        <div class="portfolio-overlay">
                            <div class="portfolio-play">▶</div>
                        </div>
                    </div>
                    <div class="portfolio-content">
                        <div class="portfolio-category">Event Production</div>
                        <h3 class="portfolio-title">Festival Musicale</h3>
                        <p class="portfolio-description">Organizzazione completa di festival con regia audio/luci, gestione artisti e coordinamento logistico.</p>
                        <a href="https://www.instagram.com/reel/CtGd2FUgkR5/?hl=it" target="_blank" class="portfolio-link">GUARDA VIDEO</a>
                    </div>
                </div>

                <div class="portfolio-item" data-category="events">
                    <div class="portfolio-image events">
                        <div class="portfolio-overlay">
                            <div class="portfolio-play">▶</div>
                        </div>
                    </div>
                    <div class="portfolio-content">
                        <div class="portfolio-category">Event Production</div>
                        <h3 class="portfolio-title">Evento Corporate</h3>
                        <p class="portfolio-description">Evento aziendale con allestimenti personalizzati, catering e intrattenimento su misura.</p>
                        <a href="https://www.instagram.com/p/DLC8VWctIu7/" target="_blank" class="portfolio-link">GUARDA VIDEO</a>
                    </div>
                </div>

                <div class="portfolio-item" data-category="events">
                    <div class="portfolio-image events">
                        <div class="portfolio-overlay">
                            <div class="portfolio-play">▶</div>
                        </div>
                    </div>
                    <div class="portfolio-content">
                        <div class="portfolio-category">Event Production</div>
                        <h3 class="portfolio-title">Festa Privata</h3>
                        <p class="portfolio-description">Organizzazione eventi privati con attenzione ai dettagli e esperienze memorabili.</p>
                        <a href="https://www.instagram.com/p/DAJ-MVqN-HL/" target="_blank" class="portfolio-link">GUARDA VIDEO</a>
                    </div>
                </div>

                <!-- E-commerce Projects -->
                <div class="portfolio-item" data-category="web">
                    <div class="portfolio-image ecommerce">
                        <div class="portfolio-overlay">
                            <div class="portfolio-play">🌐</div>
                        </div>
                    </div>
                    <div class="portfolio-content">
                        <div class="portfolio-category">E-commerce</div>
                        <h3 class="portfolio-title">Caffe Design</h3>
                        <p class="portfolio-description">E-commerce completo con design intuitivo, ottimizzazione conversioni e fotografia prodotti.</p>
                        <a href="https://www.caffe.design/" target="_blank" class="portfolio-link">VISITA SITO</a>
                    </div>
                </div>

                <div class="portfolio-item" data-category="web">
                    <div class="portfolio-image ecommerce">
                        <div class="portfolio-overlay">
                            <div class="portfolio-play">🌐</div>
                        </div>
                    </div>
                    <div class="portfolio-content">
                        <div class="portfolio-category">E-commerce</div>
                        <h3 class="portfolio-title">Gigaciao Marketplace</h3>
                        <p class="portfolio-description">Piattaforma marketplace con gestione multi-vendor e sistema di pagamenti integrato.</p>
                        <a href="https://gigaciao.com/" target="_blank" class="portfolio-link">VISITA SITO</a>
                    </div>
                </div>

                <div class="portfolio-item" data-category="web">
                    <div class="portfolio-image ecommerce">
                        <div class="portfolio-overlay">
                            <div class="portfolio-play">🌐</div>
                        </div>
                    </div>
                    <div class="portfolio-content">
                        <div class="portfolio-category">E-commerce</div>
                        <h3 class="portfolio-title">Cophouse Website</h3>
                        <p class="portfolio-description">Sito corporate con design moderno e funzionalità avanzate per l'esperienza utente.</p>
                        <a href="https://cophouse.com/" target="_blank" class="portfolio-link">VISITA SITO</a>
                    </div>
                </div>

                <div class="portfolio-item" data-category="web">
                    <div class="portfolio-image ecommerce">
                        <div class="portfolio-overlay">
                            <div class="portfolio-play">🌐</div>
                        </div>
                    </div>
                    <div class="portfolio-content">
                        <div class="portfolio-category">E-commerce</div>
                        <h3 class="portfolio-title">Milano da Scrocco</h3>
                        <p class="portfolio-description">Piattaforma dedicata agli eventi e alle offerte di Milano con sistema di geolocalizzazione.</p>
                        <a href="https://www.milanodascrocco.com/" target="_blank" class="portfolio-link">VISITA SITO</a>
                    </div>
                </div>

                <!-- Photography Projects -->
                <div class="portfolio-item" data-category="photography">
                    <div class="portfolio-image photography">
                        <div class="portfolio-overlay">
                            <div class="portfolio-play">📸</div>
                        </div>
                    </div>
                    <div class="portfolio-content">
                        <div class="portfolio-category">Studio Fotografico</div>
                        <h3 class="portfolio-title">Pixel Studio Milano</h3>
                        <p class="portfolio-description">Studio fotografico professionale da 100 mq con attrezzatura completa per ogni tipo di produzione.</p>
                        <a href="https://drive.google.com/file/d/1CgOha7mgRUxGQaGjUqcUjeBTOTsv2X_W/view?usp=drive_link" target="_blank" class="portfolio-link">VIRTUAL TOUR</a>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- CONTATTI PAGE -->
    <div id="contatti" class="page-section hidden">
        <section class="hero-section text-center">
            <h1 class="section-title">CONTATTACI</h1>
            <p class="section-description">Pronto a trasformare le tue idee in realtà? Parliamone insieme</p>
        </section>

        <div class="contact-container">
            <div class="contact-info">
                <h3>Parliamone</h3>
                <div class="contact-details">
                    <div class="contact-item">
                        <div class="contact-icon">📧</div>
                        <div class="contact-text">
                            <h4>Email</h4>
                            <p>Scrivici per discutere il tuo progetto</p>
                            <a href="mailto:info@bngagency.com">info@bngagency.com</a>
                            <p><a href="mailto:boingparty@legalmail.it">boingparty@legalmail.it</a></p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">📱</div>
                        <div class="contact-text">
                            <h4>Telefono</h4>
                            <p>Luciano Licchetta, Co-Founder & Co-CEO</p>
                            <a href="tel:+393278774647">327 877 4647</a>
                            <p>Pierandrea Melissano, Co-Founder & Co-CEO</p>
                            <a href="tel:+393209029295">320 902 9295</a>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">📍</div>
                        <div class="contact-text">
                            <h4>Sede</h4>
                            <p>Milano, Lombardia</p>
                            <p>Italia</p>
                            <p>P.IVA: 12555630966</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">🌐</div>
                        <div class="contact-text">
                            <h4>Social Media</h4>
                            <p>Seguici sui nostri canali</p>
                            <a href="https://www.instagram.com/bngagency/" target="_blank">@bngagency</a>
                        </div>
                    </div>
                </div>
            </div>

            <div class="contact-form">
                <div class="form-header">
                    <h3>Inizia il tuo progetto</h3>
                    <p>Compila il form e ti ricontatteremo entro 24 ore</p>
                </div>
                <div class="success-message" id="successMessage">
                    Grazie per averci contattato! Ti risponderemo presto.
                </div>
                <form id="contactForm">
                    <div class="form-group">
                        <label for="name">Nome e Cognome</label>
                        <input type="text" id="name" name="name" required>
                    </div>
                    <div class="form-group">
                        <label for="email">Email</label>
                        <input type="email" id="email" name="email" required>
                    </div>
                    <div class="form-group">
                        <label for="phone">Telefono</label>
                        <input type="tel" id="phone" name="phone">
                    </div>
                    <div class="form-group">
                        <label for="service">Servizio di Interesse</label>
                        <select id="service" name="service" required>
                            <option value="">Seleziona un servizio</option>
                            <option value="brand-activation">Brand Activation</option>
                            <option value="marketing">Marketing Strategies</option>
                            <option value="events">Event Production</option>
                            <option value="ecommerce">E-commerce Development</option>
                            <option value="photography">Studio Fotografico</option>
                            <option value="altro">Altro</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="message">Messaggio</label>
                        <textarea id="message" name="message" rows="5" placeholder="Raccontaci del tuo progetto..."></textarea>
                    </div>
                    <button type="submit" class="submit-button">Invia Messaggio</button>
                </form>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-brand">
                <h3>BNG <span>AGENCY</span></h3>
                <p>Un'agenzia creativa full-service che affianca brand e aziende nel rafforzare la propria presenza mediatica attraverso strategie digitali innovative e personalizzate.</p>
                <div class="social-links">
                    <a href="https://www.instagram.com/bngagency/" target="_blank" class="social-link">📷</a>
                    <a href="mailto:info@bngagency.com" class="social-link">📧</a>
                    <a href="tel:+393278774647" class="social-link">📞</a>
                </div>
            </div>
            <div class="footer-column">
                <h4>Servizi</h4>
                <ul>
                    <li><a onclick="showPage('servizi')">Brand Activation</a></li>
                    <li><a onclick="showPage('servizi')">Marketing Strategies</a></li>
                    <li><a onclick="showPage('servizi')">Event Production</a></li>
                    <li><a onclick="showPage('servizi')">E-commerce Development</a></li>
                    <li><a onclick="showPage('servizi')">Studio Fotografico</a></li>
                </ul>
            </div>
            <div class="footer-column">
                <h4>Azienda</h4>
                <ul>
                    <li><a onclick="showPage('home')">Chi Siamo</a></li>
                    <li><a onclick="showPage('portfolio')">Portfolio</a></li>
                    <li><a onclick="showPage('contatti')">Contatti</a></li>
                    <li><a href="mailto:info@bngagency.com">Carriere</a></li>
                </ul>
            </div>
        </div>
        <div class="footer-bottom">
            <p>&copy; 2024 BNG Agency. Tutti i diritti riservati. | For The Mind By Heart | P.IVA: 12555630966</p>
        </div>
    </footer>

    <script>
        // Navigation functions
        function showPage(pageId) {
            // Hide all pages
            document.querySelectorAll('.page-section').forEach(page => {
                page.classList.add('hidden');
            });
            
            // Show selected page
            document.getElementById(pageId).classList.remove('hidden');
            
            // Update nav active state
            document.querySelectorAll('.nav-menu a').forEach(link => {
                link.classList.remove('active');
            });
            document.getElementById('nav-' + pageId).classList.add('active');
            
            // Close mobile menu if open
            document.getElementById('navMenu').classList.remove('active');
            
            // Scroll to top
            window.scrollTo({top: 0, behavior: 'smooth'});
        }

        // Mobile menu toggle
        function toggleMobileMenu() {
            const navMenu = document.getElementById('navMenu');
            navMenu.classList.toggle('active');
        }

        // Portfolio filter
        function filterPortfolio(category) {
            const items = document.querySelectorAll('.portfolio-item');
            const filters = document.querySelectorAll('.portfolio-filter');
            
            // Update active filter
            filters.forEach(filter => filter.classList.remove('active'));
            event.target.classList.add('active');
            
            // Filter items
            items.forEach(item => {
                if (category === 'all' || item.dataset.category === category) {
                    item.style.display = 'block';
                    setTimeout(() => {
                        item.style.opacity = '1';
                        item.style.transform = 'translateY(0)';
                    }, 50);
                } else {
                    item.style.opacity = '0';
                    item.style.transform = 'translateY(20px)';
                    setTimeout(() => {
                        item.style.display = 'none';
                    }, 300);
                }
            });
        }

        // Contact form handling
        document.addEventListener('DOMContentLoaded', function() {
            const contactForm = document.getElementById('contactForm');
            if (contactForm) {
                contactForm.addEventListener('submit', function(e) {
                    e.preventDefault();
                    
                    // Show success message
                    document.getElementById('successMessage').style.display = 'block';
                    
                    // Reset form
                    this.reset();
                    
                    // Hide success message after 5 seconds
                    setTimeout(() => {
                        document.getElementById('successMessage').style.display = 'none';
                    }, 5000);
                });
            }
        });

        // Smooth scroll for navigation
        function smoothScrollTo(element) {
            if (element) {
                element.scrollIntoView({
                    behavior: 'smooth',
                    block: 'start'
                });
            }
        }

        // Navigation scroll effect
        let lastScrollTop = 0;
        window.addEventListener('scroll', function() {
            const nav = document.querySelector('nav');
            const scrollTop = window.pageYOffset || document.documentElement.scrollTop;
            
            if (scrollTop > lastScrollTop && scrollTop > 100) {
                nav.style.transform = 'translateY(-100%)';
            } else {
                nav.style.transform = 'translateY(0)';
            }
            
            lastScrollTop = scrollTop;
        });

        // Intersection Observer for animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('fade-in');
                }
            });
        }, observerOptions);

        // Initialize animations
        function initAnimations() {
            document.querySelectorAll('.stat-item, .value-card, .service-detail, .portfolio-item, .contact-item').forEach(el => {
                observer.observe(el);
            });
        }

        // Close mobile menu when clicking outside
        document.addEventListener('click', function(event) {
            const navMenu = document.getElementById('navMenu');
            const mobileToggle = document.querySelector('.mobile-menu-toggle');
            
            if (!navMenu.contains(event.target) && !mobileToggle.contains(event.target)) {
                navMenu.classList.remove('active');
            }
        });

        // Initialize page
        document.addEventListener('DOMContentLoaded', function() {
            // Show home page by default
            showPage('home');
            
            // Initialize animations
            initAnimations();
            
            // Add loading effect
            document.body.style.opacity = '0';
            setTimeout(() => {
                document.body.style.transition = 'opacity 0.5s ease';
                document.body.style.opacity = '1';
            }, 100);
        });

        // Handle browser back/forward buttons
        window.addEventListener('popstate', function(event) {
            if (event.state && event.state.page) {
                showPage(event.state.page);
            }
        });

        // Add to browser history
        function addToHistory(pageId) {
            history.pushState({page: pageId}, '', '#' + pageId);
        }

        // Enhanced showPage function with history
        const originalShowPage = showPage;
        showPage = function(pageId) {
            originalShowPage(pageId);
            addToHistory(pageId);
        };
    </script>
</body>
</html>
