<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Buddhashanti A/C Hiace Booking System</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);
            color: #fff;
            min-height: 100vh;
            padding: 20px;
            background-image: url('https://picsum.photos/seed/luxury/800/1200.jpg');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            position: relative;
        }
        
        body::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(15, 32, 39, 0.85);
            z-index: -1;
        }
        
        .container {
            max-width: 480px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.08);
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.4);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .header {
            background: linear-gradient(135deg, #00b09b, #96c93d);
            padding: 30px 25px;
            text-align: center;
            border-bottom: 3px solid rgba(255, 255, 255, 0.2);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        .header h1 {
            font-size: 28px;
            margin-bottom: 8px;
            color: white;
            text-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
            font-weight: 600;
            letter-spacing: 1px;
        }
        
        .header p {
            font-size: 16px;
            opacity: 0.9;
            font-weight: 300;
        }
        
        /* Premium Login Section */
        .login-container {
            padding: 30px;
            text-align: center;
            background: rgba(0, 0, 0, 0.3);
        }
        
        .login-tabs {
            display: flex;
            margin-bottom: 25px;
            margin-top: 30px;
            border-radius: 50px;
            overflow: hidden;
            background: rgba(255, 255, 255, 0.1);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        .tab {
            flex: 1;
            padding: 15px 0;
            cursor: pointer;
            transition: all 0.3s;
            font-weight: 500;
            border: none;
            background: transparent;
            color: rgba(255, 255, 255, 0.7);
            position: relative;
            overflow: hidden;
        }
        
        .tab.active {
            background: linear-gradient(to right, #00b09b, #96c93d);
            color: white;
            box-shadow: 0 4px 15px rgba(0, 176, 155, 0.4);
        }
        
        .tab.active::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 3px;
            background: rgba(255, 255, 255, 0.8);
        }
        
        .login-options {
            display: flex;
            gap: 15px;
            margin: 25px 0;
        }
        
        .login-option {
            background: linear-gradient(135deg, #ff9966, #ff5e62);
            color: white;
            border: none;
            padding: 15px 30px;
            margin: 15px 0;
            border-radius: 50px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            width: 80%;
            transition: all 0.3s;
            box-shadow: 0 8px 20px rgba(255, 94, 98, 0.4);
            position: relative;
            overflow: hidden;
        }
        
        .login-option::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: 0.5s;
        }
        
        .login-option:hover::before {
            left: 100%;
        }
        
        .login-option:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 25px rgba(255, 94, 98, 0.6);
        }
        
        .login-form {
            background: rgba(255, 255, 255, 0.08);
            padding: 25px;
            border-radius: 15px;
            margin-top: 20px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .form-group {
            margin-bottom: 20px;
            text-align: left;
            position: relative;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: rgba(255, 255, 255, 0.9);
            font-size: 14px;
        }
        
        .form-group input {
            width: 100%;
            padding: 14px;
            border: none;
            border-radius: 8px;
            background: rgba(255, 255, 255, 0.9);
            font-size: 16px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            color: #333;
            transition: all 0.3s;
        }
        
        .form-group input:focus {
            outline: none;
            box-shadow: 0 0 0 3px rgba(0, 176, 155, 0.3);
        }
        
        .btn {
            background: linear-gradient(135deg, #00b09b, #96c93d);
            color: white;
            border: none;
            padding: 14px 25px;
            border-radius: 50px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            width: 100%;
            transition: all 0.3s;
            box-shadow: 0 5px 15px rgba(0, 176, 155, 0.4);
            position: relative;
            overflow: hidden;
        }
        
        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: 0.5s;
        }
        
        .btn:hover::before {
            left: 100%;
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(0, 176, 155, 0.6);
        }
        
        .btn-forgot {
            background: transparent;
            color: #96c93d;
            padding: 10px 0;
            width: auto;
            margin-top: 10px;
            box-shadow: none;
            font-size: 14px;
            font-weight: 500;
            text-decoration: underline;
            transition: all 0.3s;
        }
        
        .btn-forgot:hover {
            background: rgba(255, 255, 255, 0.1);
            transform: none;
            box-shadow: none;
            text-decoration: none;
        }
        
        .login-options {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }
        
        .login-option {
            background: linear-gradient(135deg, #ff9966, #ff5e62);
            color: white;
            border: none;
            padding: 15px 30px;
            margin: 15px 0;
            border-radius: 50px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            flex: 1;
            transition: all 0.3s;
            box-shadow: 0 8px 20px rgba(255, 94, 98, 0.4);
            position: relative;
            overflow: hidden;
        }
        
        .login-option::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: 0.5s;
        }
        
        .login-option:hover::before {
            left: 100%;
        }
        
        .login-option:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 25px rgba(255, 94, 98, 0.6);
        }
        
        /* Premium Dashboard Styles */
        .dashboard {
            padding: 20px;
            display: none;
        }
        
        .dashboard-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            padding-bottom: 15px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.2);
        }
        
        .dashboard-menu {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            margin-bottom: 25px;
        }
        
        .menu-item {
            background: rgba(255, 255, 255, 0.08);
            padding: 18px;
            border-radius: 12px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            position: relative;
            overflow: hidden;
        }
        
        .menu-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(0, 176, 155, 0.1), rgba(150, 201, 61, 0.1));
            z-index: -1;
            transition: opacity 0.3s;
            opacity: 0;
        }
        
        .menu-item:hover::before {
            opacity: 1;
        }
        
        .menu-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 12px 25px rgba(0, 0, 0, 0.3);
        }
        
        .menu-item i {
            font-size: 24px;
            margin-bottom: 10px;
            display: block;
            color: #96c93d;
            transition: all 0.3s;
        }
        
        .menu-item:hover i {
            transform: scale(1.2);
        }
        
        /* Premium Booking Form */
        .booking-form {
            background: rgba(255, 255, 255, 0.08);
            padding: 25px;
            border-radius: 15px;
            margin: 20px 0;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .form-row {
            display: flex;
            gap: 15px;
            margin-bottom: 15px;
        }
        
        .form-row .form-group {
            flex: 1;
        }
        
        .form-control {
            width: 100%;
            padding: 14px;
            border: none;
            border-radius: 8px;
            background: rgba(255, 255, 255, 0.9);
            font-size: 16px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            color: #333;
            transition: all 0.3s;
        }
        
        .form-control:focus {
            outline: none;
            box-shadow: 0 0 0 3px rgba(0, 176, 155, 0.3);
        }
        
        /* Premium Seat Layout */
        .seat-layout {
            background: rgba(0, 0, 0, 0.2);
            padding: 30px 20px;
            border-radius: 15px;
            margin: 20px 0;
            text-align: center;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            position: relative;
        }
        
        .seat-layout::before {
            content: '';
            position: absolute;
            top: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 60%;
            height: 2px;
            background: rgba(255, 255, 255, 0.2);
        }
        
        .seat-row {
            display: flex;
            justify-content: center;
            margin-bottom: 20px;
            position: relative;
        }
        
        .seat-row:not(:last-child)::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80%;
            height: 1px;
            background: rgba(255, 255, 255, 0.1);
        }
        
        .seat {
            width: 45px;
            height: 45px;
            margin: 0 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 10px;
            cursor: pointer;
            font-weight: 600;
            font-size: 14px;
            transition: all 0.3s ease;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            position: relative;
            overflow: hidden;
            border: 2px solid transparent;
        }
        
        .seat::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.2), rgba(255, 255, 255, 0));
            opacity: 0;
            transition: opacity 0.3s;
            border-radius: 8px;
        }
        
        .seat:hover::after {
            opacity: 1;
        }
        
        .seat:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.3);
        }
        
        .seat-available {
            background: linear-gradient(135deg, #4CAF50, #8BC34A);
            color: white;
        }
        
        .seat-available:hover {
            border-color: rgba(255, 255, 255, 0.5);
        }
        
        .seat-booked {
            background: linear-gradient(135deg, #9E9E9E, #757575);
            color: white;
            cursor: not-allowed;
            text-decoration: line-through;
            opacity: 0.8;
        }
        
        .seat-selected {
            background: linear-gradient(135deg, #2196F3, #64B5F6);
            color: white;
            transform: scale(1.1);
            box-shadow: 0 0 15px rgba(33, 150, 243, 0.7);
            z-index: 2;
            border-color: rgba(255, 255, 255, 0.7);
        }
        
        .seat-driver {
            background: linear-gradient(135deg, #607D8B, #455A64);
            color: white;
            cursor: default;
            opacity: 0.9;
        }
        
        .seat-blocked {
            background: linear-gradient(135deg, #FF9800, #F57C00);
            color: white;
            cursor: not-allowed;
            text-decoration: line-through;
            opacity: 0.9;
        }
        
        .seat-special {
            background: linear-gradient(135deg, #9C27B0, #7B1FA2);
            color: white;
            cursor: not-allowed;
        }
        
        .legend {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 25px;
            flex-wrap: wrap;
        }
        
        .legend-item {
            display: flex;
            align-items: center;
            font-size: 13px;
            background: rgba(255, 255, 255, 0.1);
            padding: 8px 12px;
            border-radius: 8px;
            transition: all 0.3s;
        }
        
        .legend-item:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-2px);
        }
        
        .legend-color {
            width: 18px;
            height: 18px;
            border-radius: 4px;
            margin-right: 8px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
        }
        
        /* Premium Passenger Details */
        .passenger-details {
            background: rgba(255, 255, 255, 0.08);
            padding: 25px;
            border-radius: 15px;
            margin-bottom: 20px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .passenger-details .form-group {
            margin-bottom: 20px;
        }
        
        /* Premium Booking Confirmation */
        .booking-confirmation {
            text-align: center;
            padding: 30px;
        }
        
        .confirmation-icon {
            font-size: 80px;
            color: #96c93d;
            margin-bottom: 20px;
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }
        
        .ticket-details {
            background: rgba(0, 0, 0, 0.3);
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
            text-align: left;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .ticket-details h3 {
            margin-bottom: 15px;
            color: #96c93d;
            text-align: center;
            font-size: 20px;
            font-weight: 600;
            letter-spacing: 1px;
        }
        
        .ticket-details .booking-details {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 10px;
            font-size: 14px;
        }
        
        /* Premium View Bookings */
        .view-bookings {
            background: rgba(255, 255, 255, 0.08);
            padding: 20px;
            border-radius: 15px;
            margin-top: 20px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .booking-item {
            background: rgba(255, 255, 255, 0.08);
            padding: 15px;
            border-radius: 10px;
            margin-bottom: 15px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s;
        }
        
        .booking-item:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 15px rgba(0, 0, 0, 0.3);
        }
        
        .booking-item h3 {
            margin-bottom: 10px;
            color: #96c93d;
            font-size: 18px;
            font-weight: 600;
        }
        
        .booking-details {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 10px;
            font-size: 14px;
        }
        
        .delete-btn {
            background: linear-gradient(135deg, #ff5f6d, #ff3b4b);
            color: white;
            border: none;
            padding: 5px 10px;
            border-radius: 5px;
            font-size: 12px;
            cursor: pointer;
            margin-top: 10px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
            transition: all 0.3s;
        }
        
        .delete-btn:hover {
            background: linear-gradient(135deg, #ff3b4b, #c62828);
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
        }
        
        .clear-all-btn {
            background: linear-gradient(135deg, #ff5f6d, #ff3b4b);
            color: white;
            border: none;
            padding: 10px 15px;
            border-radius: 5px;
            font-size: 14px;
            font-weight: 600;
            cursor: pointer;
            margin-top: 15px;
            width: 100%;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
            transition: all 0.3s;
        }
        
        .clear-all-btn:hover {
            background: linear-gradient(135deg, #ff3b4b, #c62828);
            transform: translateY(-2px);
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.3);
        }
        
        .settings-item {
            background: rgba(255, 255, 255, 0.08);
            padding: 15px;
            border-radius: 12px;
            margin-bottom: 15px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .settings-item label {
            display: block;
            margin-bottom: 8px;
            color: rgba(255, 255, 255, 0.9);
        }
        
        .settings-item input {
            width: 100%;
            padding: 10px;
            border: none;
            border-radius: 8px;
            background: rgba(255, 255, 255, 0.9);
            color: #333;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }
        
        /* Until When Section */
        .until-when-section {
            background: rgba(255, 255, 255, 0.08);
            padding: 20px;
            border-radius: 15px;
            margin-bottom: 20px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .until-when-section h3 {
            margin-bottom: 15px;
            color: #96c93d;
            font-size: 20px;
            font-weight: 600;
        }
        
        .date-picker {
            width: 100%;
            padding: 12px;
            border: none;
            border-radius: 8px;
            background: rgba(255, 255, 255, 0.9);
            font-size: 16px;
            margin-bottom: 15px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            color: #333;
        }
        
        .date-picker:focus {
            outline: none;
            box-shadow: 0 0 0 3px rgba(0, 176, 155, 0.3);
        }
        
        .filter-btn {
            background: linear-gradient(135deg, #00b09b, #96c93d);
            color: white;
            border: none;
            padding: 10px 15px;
            border-radius: 5px;
            font-size: 14px;
            font-weight: 600;
            cursor: pointer;
            margin-right: 10px;
            box-shadow: 0 4px 10px rgba(0, 176, 155, 0.3);
            transition: all 0.3s;
        }
        
        .filter-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 12px rgba(0, 176, 155, 0.4);
        }
        
        .filter-btn.clear {
            background: linear-gradient(135deg, #ff5f6d, #ff3b4b);
        }
        
        .filter-btn.clear:hover {
            background: linear-gradient(135deg, #ff3b4b, #c62828);
            box-shadow: 0 6px 12px rgba(255, 59, 75, 0.4);
        }
        
        /* Date Filter Section */
        .date-filter-section {
            background: rgba(255, 255, 255, 0.08);
            padding: 20px;
            border-radius: 15px;
            margin-bottom: 20px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .date-filter-section h3 {
            margin-bottom: 15px;
            color: #96c93d;
            font-size: 20px;
            font-weight: 600;
        }
        
        .date-filter-controls {
            display: flex;
            gap: 10px;
            margin-bottom: 15px;
        }
        
        .date-filter-controls .form-group {
            flex: 1;
        }
        
        .filter-btn {
            background: linear-gradient(135deg, #00b09b, #96c93d);
            color: white;
            border: none;
            padding: 10px 15px;
            border-radius: 5px;
            font-size: 14px;
            font-weight: 600;
            cursor: pointer;
            margin-right: 10px;
            box-shadow: 0 4px 10px rgba(0, 176, 155, 0.3);
            transition: all 0.3s;
        }
        
        .filter-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 12px rgba(0, 176, 155, 0.4);
        }
        
        .filter-btn.clear {
            background: linear-gradient(135deg, #ff5f6d, #ff3b4b);
        }
        
        .filter-btn.clear:hover {
            background: linear-gradient(135deg, #ff3b4b, #c62828);
            box-shadow: 0 6px 12px rgba(255, 59, 75, 0.4);
        }
        
        /* Reserve/Release Buttons */
        .reserve-controls {
            display: flex;
            gap: 10px;
            margin-top: 15px;
        }
        
        .reserve-btn {
            flex: 1;
            background: linear-gradient(135deg, #FF9800, #F57C00);
            color: white;
            border: none;
            padding: 10px 15px;
            border-radius: 5px;
            font-size: 14px;
            font-weight: 600;
            cursor: pointer;
            box-shadow: 0 4px 10px rgba(255, 152, 0, 0.3);
            transition: all 0.3s;
        }
        
        .reserve-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 12px rgba(255, 152, 0, 0.4);
        }
        
        .release-btn {
            flex: 1;
            background: linear-gradient(135deg, #4CAF50, #8BC34A);
            color: white;
            border: none;
            padding: 10px 15px;
            border-radius: 5px;
            font-size: 14px;
            font-weight: 600;
            cursor: pointer;
            box-shadow: 0 4px 10px rgba(76, 175, 80, 0.3);
            transition: all 0.3s;
        }
        
        .release-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 12px rgba(76, 175, 80, 0.4);
        }
        
        /* Notification */
        .notification {
            position: fixed;
            top: 20px;
            right: 20px;
            padding: 15px 25px;
            border-radius: 8px;
            color: white;
            font-weight: 500;
            z-index: 1000;
            opacity: 0;
            transform: translateY(-20px);
            transition: all 0.3s ease;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
        }
        
        .notification.show {
            opacity: 1;
            transform: translateY(0);
        }
        
        .notification.success {
            background: linear-gradient(135deg, #4CAF50, #8BC34A);
        }
        
        .notification.error {
            background: linear-gradient(135deg, #F44336, #E57373);
        }
        
        /* Responsive Design */
        @media (max-width: 480px) {
            .form-row {
                flex-direction: column;
                gap: 10px;
            }
            
            .dashboard-menu {
                grid-template-columns: 1fr;
            }
            
            .date-filter-controls {
                flex-direction: column;
            }
            
            .reserve-controls {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Login Screen -->
        <div id="login-screen" class="login-container">
            <div class="header">
                <h1>Buddhashanti A/C Hiace</h1>
                <p>Premium Travel Experience</p>
            </div>
            
            <div class="login-tabs">
                <button class="tab active" onclick="showCustomerLogin()">Customer</button>
                <button class="tab" onclick="showAdminLogin()">Admin</button>
            </div>
            
            <div class="login-options">
                <button class="login-option" onclick="showCustomerLogin()">
                    <i class="fas fa-user"></i> Customer Login
                </button>
                <button class="login-option" onclick="showAdminLogin()">
                    <i class="fas fa-user-shield"></i> Admin Login
                </button>
            </div>
        </div>
        
        <!-- Customer Login Form -->
        <div id="customer-login" class="login-form" style="display: none;">
            <h2 style="margin-bottom: 20px; color: #4facfe;">Customer Login</h2>
            <div class="form-group">
                <label for="customer-username">Username</label>
                <input type="text" id="customer-username" placeholder="Enter username">
            </div>
            <div class="form-group">
                <label for="customer-password">Password</label>
                <input type="password" id="customer-password" placeholder="Enter password">
            </div>
            <button class="btn" onclick="customerLogin()">Login</button>
            <button class="btn btn-forgot" onclick="showForgotPassword()">Forgot Password?</button>
            <p style="margin-top: 15px; color: #e0e0e0;">Don't have an account? <a href="#" onclick="showSignup()" style="color: #96c93d; text-decoration: none;">Sign Up</a></p>
            <button class="btn" onclick="showSignup()" style="margin-top: 10px;">Create Account</button>
            <button class="btn back-btn" onclick="showLoginScreen()" style="margin-top: 10px; background: rgba(255, 255, 255, 0.2);">Back</button>
        </div>
        
        <!-- Signup Form -->
        <div id="signup-form" class="login-form" style="display: none;">
            <h2 style="margin-bottom: 20px; color: #4facfe;">Create Account</h2>
            <div class="form-group">
                <label for="signup-name">Full Name</label>
                <input type="text" id="signup-name" placeholder="Enter your full name">
            </div>
            <div class="form-group">
                <label for="signup-email">Email</label>
                <input type="email" id="signup-email" placeholder="Enter your email">
            </div>
            <div class="form-group">
                <label for="signup-phone">Phone Number</label>
                <input type="tel" id="signup-phone" placeholder="Enter your phone number">
            </div>
            <div class="form-group">
                <label for="signup-password">Password</label>
                <input type="password" id="signup-password" placeholder="Create a password">
            </div>
            <div class="form-group">
                <label for="signup-confirm-password">Confirm Password</label>
                <input type="password" id="signup-confirm-password" placeholder="Confirm your password">
            </div>
            <button class="btn" onclick="signup()">Sign Up</button>
            <button class="btn back-btn" onclick="showCustomerLogin()" style="margin-top: 10px; background: rgba(255, 255, 255, 0.2);">Back to Login</button>
        </div>
        
        <!-- Forgot Password Form -->
        <div id="forgot-password" class="login-form" style="display: none;">
            <h2 style="margin-bottom: 20px; color: #4facfe;">Reset Password</h2>
            <div class="form-group">
                <label for="reset-email">Email</label>
                <input type="email" id="reset-email" placeholder="Enter your email">
            </div>
            <button class="btn" onclick="resetPassword()">Reset Password</button>
            <button class="btn back-btn" onclick="showCustomerLogin()" style="margin-top: 10px; background: rgba(255, 255, 255, 0.2);">Back to Login</button>
        </div>
        
        <!-- Admin Login Form -->
        <div id="admin-login" class="login-form" style="display: none;">
            <h2 style="margin-bottom: 20px; color: #4facfe;">Admin Login</h2>
            <div class="form-group">
                <label for="admin-username">Username</label>
                <input type="text" id="admin-username" placeholder="Enter username">
            </div>
            <div class="form-group">
                <label for="admin-password">Password</label>
                <input type="password" id="admin-password" placeholder="Enter password">
            </div>
            <button class="btn" onclick="adminLogin()">Login</button>
            <button class="btn back-btn" onclick="showLoginScreen()" style="margin-top: 10px; background: rgba(255, 255, 255, 0.2);">Back</button>
        </div>
        
        <!-- Admin Dashboard -->
        <div id="admin-dashboard" class="dashboard">
            <div class="dashboard-header">
                <h2>Admin Dashboard</h2>
                <button class="btn back-btn" onclick="logout()">Logout</button>
            </div>
            
            <div class="dashboard-menu">
                <div class="menu-item" onclick="showViewBookings()">
                    <i class="fas fa-ticket-alt"></i>
                    <span>View Bookings</span>
                </div>
                <div class="menu-item" onclick="showManualBooking()">
                    <i class="fas fa-edit"></i>
                    <span>Manual Booking</span>
                </div>
                <div class="menu-item" onclick="showReserveSeats()">
                    <i class="fas fa-ban"></i>
                    <span>Reserve Seats</span>
                </div>
                <div class="menu-item" onclick="showSeatPrice()">
                    <i class="fas fa-tag"></i>
                    <span>Seat Price</span>
                </div>
                <div class="menu-item" onclick="showDiscount()">
                    <i class="fas fa-percentage"></i>
                    <span>Discount Amount</span>
                </div>
                <div class="menu-item" onclick="showPassengerCount()">
                    <i class="fas fa-users"></i>
                    <span>Count Passenger</span>
                </div>
                <div class="menu-item" onclick="showUntilWhen()">
                    <i class="fas fa-calendar-alt"></i>
                    <span>Until When</span>
                </div>
            </div>
            
            <!-- Date Filter Section -->
            <div id="date-filter" class="date-filter-section" style="display: none;">
                <h3>Filter Bookings by Date</h3>
                <div class="date-filter-controls">
                    <div class="form-group">
                        <label for="filter-start-date">Start Date</label>
                        <input type="date" id="filter-start-date" class="date-picker">
                    </div>
                    <div class="form-group">
                        <label for="filter-end-date">End Date</label>
                        <input type="date" id="filter-end-date" class="date-picker">
                    </div>
                </div>
                <button class="filter-btn" onclick="applyDateFilter()">Apply Filter</button>
                <button class="filter-btn clear" onclick="clearDateFilter()">Clear Filter</button>
            </div>
            
            <!-- View Bookings Section -->
            <div id="view-bookings" class="view-bookings" style="display: none;">
                <h3>View Bookings</h3>
                <div id="bookings-container">
                    <!-- Bookings will be populated here -->
                </div>
                <button class="clear-all-btn" onclick="clearAllBookings()">Clear All Bookings</button>
                <button class="btn back-btn" onclick="hideAllSections()">Back to Dashboard</button>
            </div>
            
            <!-- Manual Booking Section -->
            <div id="manual-booking" style="display: none;">
                <h3>Manual Booking</h3>
                <div class="seat-layout" id="manual-seat-layout">
                    <!-- Seat layout will be generated here -->
                </div>
                <div class="form-group">
                    <label for="manual-phone">Phone Number</label>
                    <input type="text" id="manual-phone" placeholder="Enter customer phone number">
                </div>
                <button class="btn" onclick="saveManualBooking()">Save Booking</button>
                <button class="btn back-btn" onclick="hideAllSections()">Back to Dashboard</button>
            </div>
            
            <!-- Reserve Seats Section -->
            <div id="reserve-seats" style="display: none;">
                <h3>Reserve Seats</h3>
                <div class="seat-layout" id="block-seat-layout">
                    <!-- Seat layout will be generated here -->
                </div>
                <div class="reserve-controls">
                    <button class="reserve-btn" onclick="reserveSelectedSeats()">Reserve Selected</button>
                    <button class="release-btn" onclick="releaseSelectedSeats()">Release Selected</button>
                </div>
                <button class="btn back-btn" onclick="hideAllSections()">Back to Dashboard</button>
            </div>
            
            <!-- Seat Price Section -->
            <div id="seat-price" style="display: none;">
                <h3>Seat Price</h3>
                <div class="settings-item">
                    <label for="price-input">Current Price: <span id="current-price">1800</span></label>
                    <input type="number" id="price-input" value="1800">
                </div>
                <button class="btn" onclick="updateSeatPrice()">Update Price</button>
                <button class="btn back-btn" onclick="hideAllSections()">Back to Dashboard</button>
            </div>
            
            <!-- Discount Amount Section -->
            <div id="discount" style="display: none;">
                <h3>Discount Amount</h3>
                <div class="settings-item">
                    <label for="discount-input">Current Discount: <span id="current-discount">0</span></label>
                    <input type="number" id="discount-input" value="0">
                </div>
                <button class="btn" onclick="updateDiscount()">Update Discount</button>
                <button class="btn back-btn" onclick="hideAllSections()">Back to Dashboard</button>
            </div>
            
            <!-- Passenger Count Section -->
            <div id="passenger-count" style="display: none;">
                <h3>Passenger Count</h3>
                <div id="passenger-list">
                    <!-- Passenger list will be populated here -->
                </div>
                <button class="btn back-btn" onclick="hideAllSections()">Back to Dashboard</button>
            </div>
            
            <!-- Until When Section -->
            <div id="until-when" class="until-when-section" style="display: none;">
                <h3>Set Booking Date Limit</h3>
                <input type="date" id="until-when-date" class="date-picker">
                <button class="filter-btn" onclick="setUntilWhenDate()">Set Date Limit</button>
                <button class="filter-btn clear" onclick="hideAllSections()">Cancel</button>
            </div>
        </div>
        
        <!-- Customer Dashboard -->
        <div id="customer-dashboard" class="dashboard">
            <div class="dashboard-header">
                <h2>Book Your Ticket</h2>
                <button class="btn back-btn" onclick="logout()">Logout</button>
            </div>
            
            <div class="booking-form">
                <div class="form-row">
                    <div class="form-group">
                        <label for="departure">Departure</label>
                        <select id="departure" class="form-control">
                            <option value="Budhabare">Budhabare</option>
                            <option value="Kathmandu">Kathmandu</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="destination">Destination</label>
                        <select id="destination" class="form-control">
                            <option value="Kathmandu">Kathmandu</option>
                            <option value="Budhabare">Budhabare</option>
                        </select>
                    </div>
                </div>
                
                <div class="form-group">
                    <label for="travel-date">Travel Date</label>
                    <input type="date" id="travel-date" class="form-control">
                </div>
                
                <button class="btn" onclick="proceedToSeatSelection()">Proceed to Seat Selection</button>
            </div>
        </div>
        
        <!-- Seat Selection Screen -->
        <div id="seat-selection" class="dashboard" style="display: none;">
            <div class="dashboard-header">
                <h2>Select Your Seat</h2>
                <button class="btn back-btn" onclick="backToCustomerDashboard()">Back</button>
            </div>
            
            <div class="seat-layout" id="seat-layout">
                <!-- Seat layout will be generated here -->
            </div>
            
            <div class="legend">
                <div class="legend-item">
                    <div class="legend-color" style="background: #4CAF50;"></div>
                    <span>Available</span>
                </div>
                <div class="legend-item">
                    <div class="legend-color" style="background: #2196F3;"></div>
                    <span>Selected</span>
                </div>
                <div class="legend-item">
                    <div class="legend-color" style="background: #9E9E9E;"></div>
                    <span>Booked</span>
                </div>
                <div class="legend-item">
                    <div class="legend-color" style="background: #607D8B;"></div>
                    <span>Driver</span>
                </div>
            </div>
            
            <div class="form-group">
                <label>Selected Seat: <span id="selected-seat-display">None</span></label>
            </div>
            
            <button class="btn" onclick="proceedToPassengerDetails()">Continue</button>
        </div>
        
        <!-- Passenger Details Screen -->
        <div id="passenger-details" class="dashboard" style="display: none;">
            <div class="dashboard-header">
                <h2>Passenger Details</h2>
                <button class="btn back-btn" onclick="backToSeatSelection()">Back</button>
            </div>
            
            <div class="passenger-details">
                <div class="form-group">
                    <label for="passenger-name">Full Name</label>
                    <input type="text" id="passenger-name" placeholder="Enter your full name">
                </div>
                
                <div class="form-group">
                    <label for="passenger-phone">Mobile Number</label>
                    <input type="tel" id="passenger-phone" placeholder="Enter your mobile number">
                </div>
                
                <div class="form-row">
                    <div class="form-group">
                        <label for="passenger-age">Age</label>
                        <input type="number" id="passenger-age" placeholder="Enter age">
                    </div>
                    <div class="form-group">
                        <label for="passenger-gender">Gender</label>
                        <select id="passenger-gender" class="form-control">
                            <option value="Male">Male</option>
                            <option value="Female">Female</option>
                            <option value="Other">Other</option>
                        </select>
                    </div>
                </div>
                
                <div class="form-group">
                    <label for="payment-mode">Payment Mode</label>
                    <select id="payment-mode" class="form-control">
                        <option value="esewa">Esewa</option>
                        <option value="khalti">Khalti</option>
                        <option value="bank-transfer">Bank Transfer</option>
                        <option value="cash">Cash</option>
                    </select>
                </div>
                
                <div class="form-group">
                    <label for="payment-type">Payment Type</label>
                    <select id="payment-type" class="form-control">
                        <option value="full">Full Payment</option>
                        <option value="cash-on-board">Cash on Board</option>
                    </select>
                </div>
                
                <div class="form-group">
                    <label>Ticket Price: NPR <span id="ticket-price">1800</span></label>
                </div>
                
                <button class="btn" onclick="confirmBooking()">Confirm Booking</button>
            </div>
        </div>
        
        <!-- Booking Confirmation Screen -->
        <div id="booking-confirmation" class="dashboard" style="display: none;">
            <div class="booking-confirmation">
                <i class="fas fa-check-circle confirmation-icon"></i>
                <h3>Your booking has been confirmed!</h3>
                <div class="ticket-details">
                    <h3>Ticket Details</h3>
                    <div id="ticket-details">
                        <!-- Ticket details will be populated here -->
                    </div>
                </div>
                <button class="btn" onclick="backToCustomerDashboard()">Back to Dashboard</button>
            </div>
        </div>
        
        <!-- Notification -->
        <div id="notification" class="notification">
            <!-- Notification message will be displayed here -->
        </div>
    </div>
    <script>
        // App State
        const appState = {
            currentScreen: 'login',
            admin: {
                username: 'Gyan',
                password: '41738@Gyan'
            },
            customer: {
                username: 'customer',
                password: '1234'
            },
            settings: {
                seatPrice: 1800,
                discountAmount: 0,
                untilWhenDate: null
            },
            bookings: [],
            blockedSeats: [],
            passengerCounts: {},
            currentBooking: {
                departure: '',
                destination: '',
                date: '',
                seat: '',
                price: 1800,
                discount: 0
            }
        };
        
        // Initialize app
        document.addEventListener('DOMContentLoaded', () => {
            // Load data from localStorage if available
            loadData();
            
            // Set min date for travel date to today
            const today = new Date().toISOString().split('T')[0];
            document.getElementById('travel-date').min = today;
            document.getElementById('travel-date').value = today;
            
            // Generate initial seat layouts
            generateSeatLayout('manual-seat-layout');
            generateSeatLayout('block-seat-layout');
            generateSeatLayout('seat-layout');
            
            // Update UI with current settings
            document.getElementById('current-price').textContent = appState.settings.seatPrice;
            document.getElementById('current-discount').textContent = appState.settings.discountAmount;
            document.getElementById('ticket-price').textContent = appState.settings.seatPrice;
        });
        
        // Load data from localStorage
        function loadData() {
            const savedBookings = localStorage.getItem('buddhashantiBookings');
            const savedSettings = localStorage.getItem('buddhashantiSettings');
            const savedBlockedSeats = localStorage.getItem('buddhashantiBlockedSeats');
            const savedPassengerCounts = localStorage.getItem('buddhashantiPassengerCounts');
            
            if (savedBookings) appState.bookings = JSON.parse(savedBookings);
            if (savedSettings) appState.settings = JSON.parse(savedSettings);
            if (savedBlockedSeats) appState.blockedSeats = JSON.parse(savedBlockedSeats);
            if (savedPassengerCounts) appState.passengerCounts = JSON.parse(savedPassengerCounts);
        }
        
        // Save data to localStorage
        function saveData() {
            localStorage.setItem('buddhashantiBookings', JSON.stringify(appState.bookings));
            localStorage.setItem('buddhashantiSettings', JSON.stringify(appState.settings));
            localStorage.setItem('buddhashantiBlockedSeats', JSON.stringify(appState.blockedSeats));
            localStorage.setItem('buddhashantiPassengerCounts', JSON.stringify(appState.passengerCounts));
        }
        
        // Screen Navigation Functions
        function showLoginScreen() {
            hideAllScreens();
            document.getElementById('login-screen').style.display = 'block';
            appState.currentScreen = 'login';
        }
        
        function showCustomerLogin() {
            hideAllScreens();
            document.getElementById('customer-login').style.display = 'block';
            appState.currentScreen = 'customer-login';
        }
        
        function showAdminLogin() {
            hideAllScreens();
            document.getElementById('admin-login').style.display = 'block';
            appState.currentScreen = 'admin-login';
        }
        
        function showSignup() {
            hideAllScreens();
            document.getElementById('signup-form').style.display = 'block';
            appState.currentScreen = 'signup';
        }
        
        function showForgotPassword() {
            hideAllScreens();
            document.getElementById('forgot-password').style.display = 'block';
            appState.currentScreen = 'forgot-password';
        }
        
        function hideAllScreens() {
            document.getElementById('login-screen').style.display = 'none';
            document.getElementById('customer-login').style.display = 'none';
            document.getElementById('signup-form').style.display = 'none';
            document.getElementById('forgot-password').style.display = 'none';
            document.getElementById('admin-login').style.display = 'none';
            document.getElementById('admin-dashboard').style.display = 'none';
            document.getElementById('customer-dashboard').style.display = 'none';
            document.getElementById('seat-selection').style.display = 'none';
            document.getElementById('passenger-details').style.display = 'none';
            document.getElementById('booking-confirmation').style.display = 'none';
        }
        
        function hideAllSections() {
            document.getElementById('view-bookings').style.display = 'none';
            document.getElementById('manual-booking').style.display = 'none';
            document.getElementById('reserve-seats').style.display = 'none';
            document.getElementById('seat-price').style.display = 'none';
            document.getElementById('discount').style.display = 'none';
            document.getElementById('passenger-count').style.display = 'none';
            document.getElementById('until-when').style.display = 'none';
            document.getElementById('date-filter').style.display = 'none';
        }
        
        function showAdminDashboard() {
            hideAllScreens();
            document.getElementById('admin-dashboard').style.display = 'block';
            appState.currentScreen = 'admin-dashboard';
        }
        
        function showCustomerDashboard() {
            hideAllScreens();
            document.getElementById('customer-dashboard').style.display = 'block';
            appState.currentScreen = 'customer-dashboard';
        }
        
        // Authentication Functions
        function adminLogin() {
            const username = document.getElementById('admin-username').value;
            const password = document.getElementById('admin-password').value;
            
            if (username === appState.admin.username && password === appState.admin.password) {
                showAdminDashboard();
                showNotification('Admin login successful!', 'success');
            } else {
                showNotification('Invalid username or password', 'error');
            }
        }
        
        function customerLogin() {
            const username = document.getElementById('customer-username').value;
            const password = document.getElementById('customer-password').value;
            
            if (username === appState.customer.username && password === appState.customer.password) {
                showCustomerDashboard();
                showNotification('Customer login successful!', 'success');
            } else {
                showNotification('Invalid username or password', 'error');
            }
        }
        
        function signup() {
            const name = document.getElementById('signup-name').value;
            const email = document.getElementById('signup-email').value;
            const phone = document.getElementById('signup-phone').value;
            const password = document.getElementById('signup-password').value;
            const confirmPassword = document.getElementById('signup-confirm-password').value;
            
            if (!name || !email || !phone || !password) {
                showNotification('Please fill in all required fields', 'error');
                return;
            }
            
            if (password !== confirmPassword) {
                showNotification('Passwords do not match', 'error');
                return;
            }
            
            // Create new customer account
            appState.customer.username = email;
            appState.customer.password = password;
            
            showNotification('Account created successfully!', 'success');
            showCustomerLogin();
        }
        
        function resetPassword() {
            const email = document.getElementById('reset-email').value;
            
            if (!email) {
                showNotification('Please enter your email', 'error');
                return;
            }
            
            // In a real app, this would send a password reset email
            showNotification('Password reset link sent to your email', 'success');
            showCustomerLogin();
        }
        
        function logout() {
            showLoginScreen();
            showNotification('Logged out successfully', 'success');
        }
        
        // Admin Functions
        function showViewBookings() {
            hideAllSections();
            document.getElementById('view-bookings').style.display = 'block';
            document.getElementById('date-filter').style.display = 'block';
            
            const container = document.getElementById('bookings-container');
            container.innerHTML = '';
            
            if (appState.bookings.length === 0) {
                container.innerHTML = '<p>No bookings found</p>';
                return;
            }
            
            appState.bookings.forEach((booking, index) => {
                const bookingEl = document.createElement('div');
                bookingEl.className = 'booking-item';
                bookingEl.innerHTML = `
                    <h3>Ticket #${index + 1}</h3>
                    <div class="booking-details">
                        <div><strong>Name:</strong> ${booking.customer.name}</div>
                        <div><strong>Phone:</strong> ${booking.customer.phone}</div>
                        <div><strong>Seat:</strong> ${booking.seat}</div>
                        <div><strong>Route:</strong> ${booking.departure} → ${booking.destination}</div>
                        <div><strong>Date:</strong> ${booking.date}</div>
                        <div><strong>Price:</strong> NPR ${booking.price}</div>
                        <div><strong>Discount:</strong> ${booking.discount > 0 ? 'NPR ' + booking.discount : 'None'}</div>
                        <div><strong>Payment:</strong> ${booking.paymentMode}</div>
                    </div>
                    <button class="delete-btn" onclick="deleteBooking(${index})">Delete</button>
                `;
                container.appendChild(bookingEl);
            });
        }
        
        function deleteBooking(index) {
            if (confirm('Are you sure you want to delete this booking?')) {
                const deletedPhone = appState.bookings[index].customer.phone;
                const deletedSeat = appState.bookings[index].seat;
                
                // Remove the booking
                appState.bookings.splice(index, 1);
                
                // Remove passenger count if exists
                if (appState.passengerCounts[deletedPhone]) {
                    delete appState.passengerCounts[deletedPhone];
                }
                
                saveData();
                showViewBookings();
                
                // Update all seat layouts to make the deleted seat available again
                updateSeatLayout('manual-seat-layout');
                updateSeatLayout('block-seat-layout');
                updateSeatLayout('seat-layout');
                
                showNotification('Booking deleted successfully', 'success');
            }
        }
        
        function clearAllBookings() {
            if (confirm('Are you sure you want to delete ALL bookings?')) {
                appState.bookings = [];
                appState.passengerCounts = {};
                saveData();
                showViewBookings();
                
                // Update all seat layouts to make all seats available again
                updateSeatLayout('manual-seat-layout');
                updateSeatLayout('block-seat-layout');
                updateSeatLayout('seat-layout');
                
                showNotification('All bookings cleared successfully', 'success');
            }
        }
        
        function showManualBooking() {
            hideAllSections();
            document.getElementById('manual-booking').style.display = 'block';
            
            // Update manual seat layout
            updateSeatLayout('manual-seat-layout');
        }
        
        function showReserveSeats() {
            hideAllSections();
            document.getElementById('reserve-seats').style.display = 'block';
            
            // Update reserve seat layout
            updateSeatLayout('block-seat-layout');
        }
        
        function showSeatPrice() {
            hideAllSections();
            document.getElementById('seat-price').style.display = 'block';
            document.getElementById('price-input').value = appState.settings.seatPrice;
        }
        
        function showDiscount() {
            hideAllSections();
            document.getElementById('discount').style.display = 'block';
            document.getElementById('discount-input').value = appState.settings.discountAmount;
        }
        
        function showPassengerCount() {
            hideAllSections();
            document.getElementById('passenger-count').style.display = 'block';
            
            const container = document.getElementById('passenger-list');
            container.innerHTML = '';
            
            if (Object.keys(appState.passengerCounts).length === 0) {
                container.innerHTML = '<p>No passenger data found</p>';
                return;
            }
            
            for (const [phone, data] of Object.entries(appState.passengerCounts)) {
                const passengerEl = document.createElement('div');
                passengerEl.className = 'booking-item';
                passengerEl.innerHTML = `
                    <h3>Passenger: ${data.name}</h3>
                    <div class="booking-details">
                        <div><strong>Phone:</strong> ${phone}</div>
                        <div><strong>Travel Count:</strong> ${data.count}</div>
                        <div><strong>Last Travel:</strong> ${data.lastTravel}</div>
                        <div><strong>Eligible for Discount:</strong> ${data.count >= 3 ? 'Yes' : 'No'}</div>
                    </div>
                `;
                container.appendChild(passengerEl);
            }
        }
        
        function showUntilWhen() {
            hideAllSections();
            document.getElementById('until-when').style.display = 'block';
            
            // Set default date if none is set
            if (!appState.settings.untilWhenDate) {
                const today = new Date().toISOString().split('T')[0];
                document.getElementById('until-when-date').value = today;
            } else {
                document.getElementById('until-when-date').value = appState.settings.untilWhenDate;
            }
        }
        
        function setUntilWhenDate() {
            const date = document.getElementById('until-when-date').value;
            if (!date) {
                showNotification('Please select a date', 'error');
                return;
            }
            
            appState.settings.untilWhenDate = date;
            saveData();
            showNotification('Date limit set successfully', 'success');
            hideAllSections();
            showAdminDashboard();
        }
        
        function updateSeatPrice() {
            const newPrice = parseInt(document.getElementById('price-input').value);
            if (isNaN(newPrice) || newPrice <= 0) {
                showNotification('Please enter a valid price', 'error');
                return;
            }
            
            appState.settings.seatPrice = newPrice;
            document.getElementById('current-price').textContent = newPrice;
            document.getElementById('ticket-price').textContent = newPrice;
            saveData();
            showNotification('Seat price updated successfully', 'success');
        }
        
        function updateDiscount() {
            const newDiscount = parseInt(document.getElementById('discount-input').value);
            if (isNaN(newDiscount) || newDiscount < 0) {
                showNotification('Please enter a valid discount amount', 'error');
                return;
            }
            
            appState.settings.discountAmount = newDiscount;
            document.getElementById('current-discount').textContent = newDiscount;
            saveData();
            showNotification('Discount amount updated successfully', 'success');
        }
        
        function saveManualBooking() {
            const seat = appState.currentBooking.seat;
            const phone = document.getElementById('manual-phone').value;
            
            if (!seat) {
                showNotification('Please select a seat', 'error');
                return;
            }
            
            if (!phone) {
                showNotification('Please enter phone number', 'error');
                return;
            }
            
            // Find customer by phone
            const customer = appState.bookings.find(b => b.customer.phone === phone);
            
            const newBooking = {
                customer: customer ? customer.customer : {
                    name: 'Manual Booking',
                    phone: phone,
                    age: 0,
                    gender: 'Not specified'
                },
                seat: seat,
                departure: 'Budhabare',
                destination: 'Kathmandu',
                date: new Date().toISOString().split('T')[0],
                price: appState.settings.seatPrice,
                discount: 0,
                paymentMode: 'Manual',
                paymentType: 'Full Payment',
                status: 'confirmed'
            };
            
            appState.bookings.push(newBooking);
            saveData();
            updateSeatLayout('manual-seat-layout');
            showNotification('Manual booking saved successfully', 'success');
        }
        
        // Seat Layout Functions
        function generateSeatLayout(containerId) {
            const container = document.getElementById(containerId);
            container.innerHTML = '';
            
            // Row 1: A, B, Driver
            const row1 = document.createElement('div');
            row1.className = 'seat-row';
            row1.innerHTML = `
                <div class="seat seat-available" data-seat="A" style="margin-left: 20px;">A</div>
                <div class="seat seat-available" data-seat="B" style="margin-left: 60px;">B</div>
                <div class="seat seat-driver" style="margin-left: 60px;">Driver</div>
            `;
            container.appendChild(row1);
            
            // Row 2: 1, 2, 3
            const row2 = document.createElement('div');
            row2.className = 'seat-row';
            row2.innerHTML = `
                <div class="seat" data-seat="1" style="margin-left: 100px;">1</div>
                <div class="seat" data-seat="2" style="margin-left: 40px;">2</div>
                <div class="seat" data-seat="3" style="margin-left: 40px;">3</div>
            `;
            container.appendChild(row2);
            
            // Row 3: 4, 5, 6
            const row3 = document.createElement('div');
            row3.className = 'seat-row';
            row3.innerHTML = `
                <div class="seat" data-seat="4" style="margin-left: 100px;">4</div>
                <div class="seat" data-seat="5" style="margin-left: 40px;">5</div>
                <div class="seat" data-seat="6" style="margin-left: 40px;">6</div>
            `;
            container.appendChild(row3);
            
            // Row 4: 7, 8, 9
            const row4 = document.createElement('div');
            row4.className = 'seat-row';
            row4.innerHTML = `
                <div class="seat" data-seat="7" style="margin-left: 100px;">7</div>
                <div class="seat" data-seat="8" style="margin-left: 40px;">8</div>
                <div class="seat" data-seat="9" style="margin-left: 40px;">9</div>
            `;
            container.appendChild(row4);
            
            // Row 5: 10, 11, 12, 13
            const row5 = document.createElement('div');
            row5.className = 'seat-row';
            row5.innerHTML = `
                <div class="seat" data-seat="10" style="margin-left: 20px;">10</div>
                <div class="seat" data-seat="11" style="margin-left: 40px;">11</div>
                <div class="seat" data-seat="12" style="margin-left: 40px;">12</div>
                <div class="seat" data-seat="13" style="margin-left: 40px;">13</div>
            `;
            container.appendChild(row5);
            
            // Add event listeners to seats
            const seats = container.querySelectorAll('.seat:not(.seat-driver)');
            seats.forEach(seat => {
                seat.addEventListener('click', function() {
                    const seatId = this.getAttribute('data-seat');
                    const containerType = containerId.split('-')[0];
                    
                    if (containerType === 'manual') {
                        handleManualSeatClick(seatId);
                    } else if (containerType === 'block') {
                        handleReserveSeatClick(seatId);
                    } else {
                        handleSeatSelection(seatId);
                    }
                });
            });
        }
        
        function updateSeatLayout(containerId) {
            const seats = document.querySelectorAll(`#${containerId} .seat:not(.seat-driver)`);
            
            seats.forEach(seat => {
                const seatId = seat.getAttribute('data-seat');
                
                // Reset classes
                seat.className = 'seat';
                
                // Check if seat is booked
                const isBooked = appState.bookings.some(b => b.seat === seatId);
                if (isBooked) {
                    seat.classList.add('seat-booked');
                    return;
                }
                
                // Check if seat is blocked
                const isBlocked = appState.blockedSeats.includes(seatId);
                if (isBlocked) {
                    // For user panel, show blocked seats as booked
                    if (containerId === 'seat-layout') {
                        seat.classList.add('seat-booked');
                    } else {
                        // For admin panels, show as orange
                        seat.classList.add('seat-blocked');
                    }
                    return;
                }
                
                // Available seat
                seat.classList.add('seat-available');
            });
        }
        
        function handleManualSeatClick(seatId) {
            const seats = document.querySelectorAll('#manual-seat-layout .seat:not(.seat-driver)');
            
            seats.forEach(seat => {
                const currentSeatId = seat.getAttribute('data-seat');
                
                if (currentSeatId === seatId) {
                    // Toggle selection
                    if (seat.classList.contains('seat-selected')) {
                        seat.classList.remove('seat-selected');
                        seat.classList.add('seat-available');
                        appState.currentBooking.seat = '';
                    } else {
                        // Deselect other seats
                        seats.forEach(s => {
                            s.classList.remove('seat-selected');
                            s.classList.add('seat-available');
                        });
                        
                        seat.classList.remove('seat-available');
                        seat.classList.add('seat-selected');
                        appState.currentBooking.seat = seatId;
                    }
                }
            });
        }
        
        function handleReserveSeatClick(seatId) {
            const seat = document.querySelector(`#block-seat-layout .seat[data-seat="${seatId}"]`);
            if (!seat) return;

            // If the seat is booked (grey), we cannot select it
            if (seat.classList.contains('seat-booked')) {
                return;
            }

            // Toggle selection
            if (seat.classList.contains('seat-selected')) {
                seat.classList.remove('seat-selected');
                // Revert to original state
                if (appState.blockedSeats.includes(seatId)) {
                    seat.classList.add('seat-blocked');
                } else {
                    seat.classList.add('seat-available');
                }
            } else {
                // Remove existing state classes and add selection
                seat.classList.remove('seat-available', 'seat-blocked');
                seat.classList.add('seat-selected');
            }
        }
        
        function reserveSelectedSeats() {
            const selectedSeats = document.querySelectorAll('#block-seat-layout .seat-selected');
            const toReserve = [];

            selectedSeats.forEach(seat => {
                const seatId = seat.getAttribute('data-seat');
                // Only reserve seats that are currently available (not already reserved)
                if (!appState.blockedSeats.includes(seatId)) {
                    toReserve.push(seatId);
                }
            });

            if (toReserve.length === 0) {
                showNotification('No available seats selected for reservation', 'error');
                return;
            }

            // Add to blockedSeats
            toReserve.forEach(seatId => {
                appState.blockedSeats.push(seatId);
            });

            saveData();
            updateSeatLayout('block-seat-layout');
            showNotification(`${toReserve.length} seat(s) reserved successfully`, 'success');
        }
        
        function releaseSelectedSeats() {
            const selectedSeats = document.querySelectorAll('#block-seat-layout .seat-selected');
            const toRelease = [];

            selectedSeats.forEach(seat => {
                const seatId = seat.getAttribute('data-seat');
                // Only release seats that are currently reserved
                if (appState.blockedSeats.includes(seatId)) {
                    toRelease.push(seatId);
                }
            });

            if (toRelease.length === 0) {
                showNotification('No reserved seats selected for release', 'error');
                return;
            }

            // Remove from blockedSeats
            toRelease.forEach(seatId => {
                const index = appState.blockedSeats.indexOf(seatId);
                if (index !== -1) {
                    appState.blockedSeats.splice(index, 1);
                }
            });

            saveData();
            updateSeatLayout('block-seat-layout');
            showNotification(`${toRelease.length} seat(s) released successfully`, 'success');
        }
        
        function handleSeatSelection(seatId) {
            const seats = document.querySelectorAll('#seat-layout .seat:not(.seat-driver)');
            
            seats.forEach(seat => {
                const currentSeatId = seat.getAttribute('data-seat');
                
                if (currentSeatId === seatId) {
                    // Only allow selection of available seats
                    if (seat.classList.contains('seat-available')) {
                        // Toggle selection
                        if (seat.classList.contains('seat-selected')) {
                            seat.classList.remove('seat-selected');
                            seat.classList.add('seat-available');
                            appState.currentBooking.seat = '';
                        } else {
                            // Deselect other seats
                            seats.forEach(s => {
                                s.classList.remove('seat-selected');
                                if (!s.classList.contains('seat-booked')) {
                                    s.classList.add('seat-available');
                                }
                            });
                            
                            seat.classList.remove('seat-available');
                            seat.classList.add('seat-selected');
                            appState.currentBooking.seat = seatId;
                        }
                    }
                }
            });
            
            document.getElementById('selected-seat-display').textContent = appState.currentBooking.seat || 'None';
        }
        
        // Customer Booking Flow
        function proceedToSeatSelection() {
            const departure = document.getElementById('departure').value;
            const destination = document.getElementById('destination').value;
            const date = document.getElementById('travel-date').value;
            
            if (departure === destination) {
                showNotification('Departure and destination cannot be the same', 'error');
                return;
            }
            
            appState.currentBooking.departure = departure;
            appState.currentBooking.destination = destination;
            appState.currentBooking.date = date;
            
            hideAllScreens();
            document.getElementById('seat-selection').style.display = 'block';
            appState.currentScreen = 'seat-selection';
            
            // Update seat layout with current bookings
            updateSeatLayout('seat-layout');
        }
        
        function backToCustomerDashboard() {
            showCustomerDashboard();
        }
        
        function backToSeatSelection() {
            hideAllScreens();
            document.getElementById('seat-selection').style.display = 'block';
            appState.currentScreen = 'seat-selection';
        }
        
        function proceedToPassengerDetails() {
            if (!appState.currentBooking.seat) {
                showNotification('Please select a seat', 'error');
                return;
            }
            
            hideAllScreens();
            document.getElementById('passenger-details').style.display = 'block';
            appState.currentScreen = 'passenger-details';
        }
        
        function confirmBooking() {
            const name = document.getElementById('passenger-name').value;
            const phone = document.getElementById('passenger-phone').value;
            const age = document.getElementById('passenger-age').value;
            const gender = document.getElementById('passenger-gender').value;
            const paymentMode = document.getElementById('payment-mode').value;
            const paymentType = document.getElementById('payment-type').value;
            
            if (!name || !phone || !age) {
                showNotification('Please fill in all required fields', 'error');
                return;
            }
            
            // Check for passenger discount
            let discount = 0;
            if (appState.passengerCounts[phone]) {
                if (appState.passengerCounts[phone].count >= 3) {
                    discount = appState.settings.discountAmount;
                }
            }
            
            const newBooking = {
                customer: {
                    name,
                    phone,
                    age,
                    gender
                },
                seat: appState.currentBooking.seat,
                departure: appState.currentBooking.departure,
                destination: appState.currentBooking.destination,
                date: appState.currentBooking.date,
                price: appState.settings.seatPrice,
                discount,
                paymentMode,
                paymentType,
                status: 'confirmed'
            };
            
            appState.bookings.push(newBooking);
            
            // Update passenger count
            if (!appState.passengerCounts[phone]) {
                appState.passengerCounts[phone] = {
                    name,
                    count: 1,
                    lastTravel: new Date().toISOString().split('T')[0]
                };
            } else {
                appState.passengerCounts[phone].count++;
                appState.passengerCounts[phone].lastTravel = new Date().toISOString().split('T')[0];
            }
            
            saveData();
            
            // Show confirmation
            showBookingConfirmation(newBooking);
        }
        
        function showBookingConfirmation(booking) {
            hideAllScreens();
            document.getElementById('booking-confirmation').style.display = 'block';
            appState.currentScreen = 'booking-confirmation';
            
            const ticketDetails = document.getElementById('ticket-details');
            ticketDetails.innerHTML = `
                <p><strong>Ticket Number:</strong> #${appState.bookings.length}</p>
                <p><strong>Name:</strong> ${booking.customer.name}</p>
                <p><strong>Phone:</strong> ${booking.customer.phone}</p>
                <p><strong>Route:</strong> ${booking.departure} → ${booking.destination}</p>
                <p><strong>Date:</strong> ${booking.date}</p>
                <p><strong>Seat:</strong> ${booking.seat}</p>
                <p><strong>Price:</strong> NPR ${booking.price}</p>
                ${booking.discount > 0 ? `<p><strong>Discount:</strong> NPR ${booking.discount}</p>` : ''}
                <p><strong>Total:</strong> NPR ${booking.price - booking.discount}</p>
                <p><strong>Payment:</strong> ${booking.paymentMode}</p>
                <p><strong>Payment Type:</strong> ${booking.paymentType}</p>
            `;
        }
        
        // Date Filter Functions
        function applyDateFilter() {
            const startDate = document.getElementById('filter-start-date').value;
            const endDate = document.getElementById('filter-end-date').value;
            
            if (!startDate || !endDate) {
                showNotification('Please select both start and end dates', 'error');
                return;
            }
            
            // Convert dates to Date objects for comparison
            const start = new Date(startDate);
            const end = new Date(endDate);
            end.setHours(23, 59, 59, 999); // Set end date to end of day
            
            let filteredBookings = appState.bookings.filter(booking => {
                const bookingDate = new Date(booking.date);
                return bookingDate >= start && bookingDate <= end;
            });
            
            const container = document.getElementById('bookings-container');
            container.innerHTML = '';
            
            if (filteredBookings.length === 0) {
                container.innerHTML = '<p>No bookings found for the selected date range</p>';
                return;
            }
            
            filteredBookings.forEach((booking, index) => {
                const originalIndex = appState.bookings.findIndex(b => b === booking);
                const bookingEl = document.createElement('div');
                bookingEl.className = 'booking-item';
                bookingEl.innerHTML = `
                    <h3>Ticket #${originalIndex + 1}</h3>
                    <div class="booking-details">
                        <div><strong>Name:</strong> ${booking.customer.name}</div>
                        <div><strong>Phone:</strong> ${booking.customer.phone}</div>
                        <div><strong>Seat:</strong> ${booking.seat}</div>
                        <div><strong>Route:</strong> ${booking.departure} → ${booking.destination}</div>
                        <div><strong>Date:</strong> ${booking.date}</div>
                        <div><strong>Price:</strong> NPR ${booking.price}</div>
                        <div><strong>Discount:</strong> ${booking.discount > 0 ? 'NPR ' + booking.discount : 'None'}</div>
                        <div><strong>Payment:</strong> ${booking.paymentMode}</div>
                    </div>
                    <button class="delete-btn" onclick="deleteBooking(${originalIndex})">Delete</button>
                `;
                container.appendChild(bookingEl);
            });
        }
        
        function clearDateFilter() {
            document.getElementById('filter-start-date').value = '';
            document.getElementById('filter-end-date').value = '';
            showViewBookings(); // Refresh the view with all bookings
        }
        
        // Utility Functions
        function showNotification(message, type) {
            const notification = document.getElementById('notification');
            notification.textContent = message;
            notification.className = `notification ${type}`;
            notification.classList.add('show');
            
            setTimeout(() => {
                notification.classList.remove('show');
            }, 3000);
        }
    </script>
</body>
</html>
