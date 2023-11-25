import React, { useState } from 'react';

function App() {
    const [member, setMember] = useState({ account: '', password: '' });

    const handleLogin = () => {
        if (member.account === 'Kenny2023@gmail.com' && member.password === '123456') {
            alert('登入成功~~');
        } else {
            alert('登入失敗，請確認您的帳號、密碼是否正確!!');
        }
    };

    const handleChange = (e) => {
        setMember({ ...member, [e.target.name]: e.target.value });
    };

    return (
        <div>
            <input
                type="text"
                placeholder="請輸入帳號: "
                name="account"
                value={member.account}
                onChange={handleChange}
            />
            <br />
            <input
                type="text"
                placeholder="請輸入密碼: "
                name="password"
                value={member.password}
                onChange={handleChange}
            />
            <br />
            <button type="button" onClick={handleLogin}>送出</button>
        </div>
    );
}