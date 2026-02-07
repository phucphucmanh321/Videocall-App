<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Connect - Họp Trực Tuyến</title>

    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script src="https://download.agora.io/sdk/release/AgoraRTC_N-4.18.2.js"></script>

    <style>
        :root {
            --brand: #4f46e5;
            --brand-hover: #4338ca;
            --bg-page: #f8fafc;
            --card-bg: #ffffff;
            --text-main: #1e293b;
            --text-sub: #64748b;
            --danger: #ef4444;
            --success: #22c55e;
            --shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.05), 0 8px 10px -6px rgba(0, 0, 0, 0.05);
        }

        * { box-sizing: border-box; transition: all 0.2s ease; }
        
        body {
            margin: 0; height: 100vh; font-family: 'Plus Jakarta Sans', sans-serif;
            background-color: var(--bg-page); color: var(--text-main);
            display: flex; flex-direction: column; overflow: hidden;
        }

        /* --- LOBBY SCREEN --- */
        #lobby-screen {
            flex: 1; display: flex; align-items: center; justify-content: center;
            background: linear-gradient(135deg, #f8fafc 0%, #e2e8f0 100%);
        }

        .join-container {
            background: var(--card-bg); padding: 48px; border-radius: 32px;
            box-shadow: var(--shadow); width: 100%; max-width: 400px; text-align: center;
            border: 1px solid rgba(255,255,255,0.8);
        }

        .app-logo {
            width: 64px; height: 64px; background: var(--brand); color: white;
            display: flex; align-items: center; justify-content: center;
            border-radius: 18px; margin: 0 auto 24px; font-size: 28px;
            box-shadow: 0 10px 15px -3px rgba(79, 70, 229, 0.3);
        }

        .join-container h2 { margin: 0 0 8px; font-weight: 700; font-size: 24px; }
        .join-container p { color: var(--text-sub); margin-bottom: 32px; font-size: 15px; }

        .input-group { position: relative; margin-bottom: 24px; }
        .input-field {
            width: 100%; padding: 16px 20px; border-radius: 16px;
            border: 2px solid #e2e8f0; font-size: 16px; font-family: inherit;
            outline: none; background: #f1f5f9;
        }
        .input-field:focus { border-color: var(--brand); background: #fff; }

        .btn-join {
            width: 100%; padding: 16px; border-radius: 16px; border: none;
            background: var(--brand); color: white; font-weight: 600;
            font-size: 16px; cursor: pointer; display: flex; align-items: center; justify-content: center; gap: 10px;
        }
        .btn-join:hover { background: var(--brand-hover); transform: translateY(-2px); }

        /* --- ROOM SCREEN --- */
        #room-screen {
            flex: 1; display: none; flex-direction: column; position: relative;
            background: #111827; /* Nền tối khi vào họp để nổi bật video */
        }

        #video-grid {
            flex: 1; display: grid; gap: 20px; padding: 20px;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            align-content: center; justify-content: center;
            max-width: 1400px; margin: 0 auto; width: 100%;
        }

        .video-wrapper {
            position: relative; aspect-ratio: 16/9; background: #1f2937;
            border-radius: 24px; overflow: hidden; box-shadow: 0 20px 25px -5px rgba(0,0,0,0.3);
        }

        .video-player { width: 100%; height: 100%; object-fit: cover; }

        .user-label {
            position: absolute; bottom: 16px; left: 16px;
            background: rgba(0, 0, 0, 0.5); backdrop-filter: blur(8px);
            color: white; padding: 6px 16px; border-radius: 12px;
            font-size: 13px; font-weight: 500; display: flex; align-items: center; gap: 8px;
        }

        /* --- CONTROLS --- */
        .controls-bar {
            position: absolute; bottom: 30px; left: 50%; transform: translateX(-50%);
            display: flex; gap: 16px; padding: 12px 24px;
            background: rgba(255, 255, 255, 0.1); backdrop-filter: blur(20px);
            border-radius: 24px; border: 1px solid rgba(255, 255, 255, 0.2);
            z-index: 10;
        }

        .btn-control {
            width: 52px; height: 52px; border-radius: 16px; border: none;
            cursor: pointer; font-size: 20px; display: flex; 
            align-items: center; justify-content: center;
            background: rgba(255,255,255,0.2); color: white;
        }

        .btn-control:hover { background: rgba(255,255,255,0.3); }
        
        .btn-control.off { background: var(--danger); color: white; }
        
        .btn-control.btn-leave {
            background: var(--danger); width: 64px; border-radius: 16px;
        }
        .btn-control.btn-leave:hover { background: #dc2626; transform: scale(1.05); }

        /* Responsive cho mobile */
        @media (max-width: 600px) {
            #video-grid { grid-template-columns: 1fr; padding: 10px; }
            .video-wrapper { aspect-ratio: 4/3; }
        }
    </style>
</head>

<body>

    <div id="lobby-screen">
        <div class="join-container">
            <div class="app-logo"><i class="fa-solid fa-bolt-lightning"></i></div>
            <h2>Bắt đầu họp</h2>
            <p>Kết nối với đồng nghiệp ngay lập tức</p>
            
            <div class="input-group">
                <input id="username" class="input-field" placeholder="Tên của bạn là gì?" autocomplete="off">
            </div>
            
            <button class="btn-join" onclick="joinMeeting()">
                Tham gia cuộc họp <i class="fa-solid fa-arrow-right"></i>
            </button>
        </div>
    </div>

    <div id="room-screen">
        <div id="video-grid"></div>

        <div class="controls-bar">
            <button id="btn-mic" class="btn-control" onclick="toggleMic()">
                <i class="fa-solid fa-microphone"></i>
            </button>
            <button id="btn-cam" class="btn-control" onclick="toggleCam()">
                <i class="fa-solid fa-video"></i>
            </button>
            <button class="btn-control btn-leave" onclick="leaveMeeting()">
                <i class="fa-solid fa-phone-slash"></i>
            </button>
        </div>
    </div>

    <script>
        const APP_ID = "efb89c2eef5f4dd3a578e87f0207bee3";
        const CHANNEL = "phong-goi-nhom";
        const TOKEN = null;

        const client = AgoraRTC.createClient({ mode: "rtc", codec: "vp8" });
        let localTracks = { audioTrack: null, videoTrack: null };
        let myName = "", myUid = null;
        let isMicOn = true, isCamOn = true;

        async function joinMeeting() {
            const name = document.getElementById("username").value.trim();
            if (!name) return alert("Vui lòng nhập tên");

            myName = name;
            document.getElementById("lobby-screen").style.display = "none";
            document.getElementById("room-screen").style.display = "flex";

            await startAgora();
        }

        async function startAgora() {
            try {
                await navigator.mediaDevices.getUserMedia({ video: true, audio: true });
                myUid = await client.join(APP_ID, CHANNEL, TOKEN, null);

                localTracks.audioTrack = await AgoraRTC.createMicrophoneAudioTrack();
                localTracks.videoTrack = await AgoraRTC.createCameraVideoTrack();
                addVideoBlock(myUid, myName + " (Bạn)");
                localTracks.videoTrack.play("user-" + myUid);
                
                await client.publish([localTracks.audioTrack, localTracks.videoTrack]);
                console.log(localTracks);
            } catch (err) {
                console.error(err);
                alert("❌ Lỗi: Không thể truy cập Camera/Mic.");
                leaveMeeting();
            }
        }

        function addVideoBlock(uid, name) {
            if (document.getElementById("user-" + uid)) return;

            const wrap = document.createElement("div");
            wrap.className = "video-wrapper";
            wrap.id = "wrap-" + uid;

            const v = document.createElement("div");
            v.id = "user-" + uid;
            v.className = "video-player";

            const label = document.createElement("div");
            label.className = "user-label";
            label.innerHTML = `<i class="fa-solid fa-circle-user"></i> <span>${name}</span>`;

            wrap.append(v, label);
            document.getElementById("video-grid").append(wrap);
        }

        client.on("user-published", async (user, mediaType) => {
            await client.subscribe(user, mediaType);
            if (mediaType === "video") {
                addVideoBlock(user.uid, "Thành viên");
                user.videoTrack.play("user-" + user.uid);
            }
            if (mediaType === "audio") user.audioTrack.play();
        });

        client.on("user-unpublished", user => {
            const el = document.getElementById("wrap-" + user.uid);
            if (el) el.remove();
        });

        async function toggleMic() {
            isMicOn = !isMicOn;
            await localTracks.audioTrack.setEnabled(isMicOn);
            const btn = document.getElementById("btn-mic");
            btn.classList.toggle("off", !isMicOn);
            btn.innerHTML = isMicOn ? '<i class="fa-solid fa-microphone"></i>' : '<i class="fa-solid fa-microphone-slash"></i>';
        }

        async function toggleCam() {
            isCamOn = !isCamOn;
            await localTracks.videoTrack.setEnabled(isCamOn);
            const btn = document.getElementById("btn-cam");
            btn.classList.toggle("off", !isCamOn);
            btn.innerHTML = isCamOn ? '<i class="fa-solid fa-video"></i>' : '<i class="fa-solid fa-video-slash"></i>';
        }

        async function leaveMeeting() {
            localTracks.audioTrack?.close();
            localTracks.videoTrack?.close();
            await client.leave();
            location.reload();
        }
    </script>
</body>
</html>