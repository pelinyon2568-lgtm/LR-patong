<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LR Executive Dashboard</title>
    
    <link href="https://fonts.googleapis.com/css2?family=Prompt:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Prompt', 'sans-serif'],
                    },
                    colors: {
                        navy: '#0a192f',
                        blue: '#1e3a8a',
                        teal: '#0d9488',
                        amber: '#f59e0b',
                        red: '#ef4444',
                        lightgray: '#f3f4f6'
                    }
                }
            }
        }
    </script>
    
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

    <style>
        body { background-color: #f3f4f6; color: #1f2937; }
        .card { background: white; border-radius: 0.5rem; box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1); padding: 1.5rem; }
        .red-flag { border-left: 4px solid #ef4444; }
        .amber-flag { border-left: 4px solid #f59e0b; }
        .teal-flag { border-left: 4px solid #0d9488; }
        .section-title { font-size: 1.25rem; font-weight: 600; color: #0a192f; margin-bottom: 1rem; border-bottom: 2px solid #e5e7eb; padding-bottom: 0.5rem; }
        .progress-bar-bg { background-color: #e5e7eb; border-radius: 9999px; height: 0.75rem; width: 100%; overflow: hidden; }
        .progress-bar-fill { height: 100%; border-radius: 9999px; display: flex; align-items: center; justify-content: center; font-size: 0.5rem; color: white; }
    </style>
</head>
<body class="antialiased">

    <div class="bg-red text-white text-center py-2 px-4 text-sm font-medium w-full z-50">
        <i class="fas fa-exclamation-triangle mr-2"></i> Dashboard นี้จัดทำขึ้นเพื่อการฝึกอบรมและการอภิปรายเชิงบริหารเท่านั้น ไม่ใช่ข้อมูลเฝ้าระวังโรคจริง และไม่ใช้สำหรับการวินิจฉัยหรือรักษาผู้ป่วย
    </div>

    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-6">
        
        <div class="flex flex-col md:flex-row justify-between items-start md:items-center mb-6">
            <div>
                <h1 class="text-3xl font-bold text-navy">Labor & Delivery (LR) Executive Dashboard</h1>
                <p class="text-gray-600 mt-1">สรุปข้อมูลสถานการณ์การคลอดและทรัพยากร สำหรับผู้บริหารระดับต้น</p>
            </div>
            <div class="mt-4 md:mt-0 text-right">
                <div class="bg-navy text-white px-4 py-2 rounded-lg inline-block shadow">
                    <span class="text-sm block text-gray-300">ข้อมูล ณ วันที่</span>
                    <span class="font-semibold" id="currentDate">21 พฤษภาคม 2569</span>
                </div>
            </div>
        </div>

        <div class="bg-blue text-white rounded-lg p-4 mb-6 shadow-md flex flex-col md:flex-row gap-4">
            <div class="flex-1">
                <h3 class="font-bold text-teal-300"><i class="fas fa-search mr-2"></i>สถานการณ์ (Situation)</h3>
                <p class="text-sm mt-1">อัตรากำลังแผนก LR ต่ำกว่าเกณฑ์เป้าหมาย (82.6%) ขณะที่แผนกหลังคลอด (PP) ภาระงานเกินขีดจำกัด (117.7%) อัตราการคลอดปกติอยู่ที่ 55.4%</p>
            </div>
            <div class="flex-1 border-t md:border-t-0 md:border-l border-blue-400 pt-4 md:pt-0 md:pl-4">
                <h3 class="font-bold text-amber-300"><i class="fas fa-bolt mr-2"></i>ผลกระทบ (Impact)</h3>
                <p class="text-sm mt-1">พยาบาลแผนกหลังคลอดเสี่ยงต่อภาวะ Burnout อาจกระทบความปลอดภัยผู้ป่วย ส่วนงานส่งต่อ (Refer) ยังควบคุมได้ดีที่ 1.24%</p>
            </div>
            <div class="flex-1 border-t md:border-t-0 md:border-l border-blue-400 pt-4 md:pt-0 md:pl-4">
                <h3 class="font-bold text-red-300"><i class="fas fa-gavel mr-2"></i>การตัดสินใจ (Action)</h3>
                <p class="text-sm mt-1">อนุมัติการเกลี่ยอัตรากำลังชั่วคราวจาก LR สู่ PP และติดตามผู้ป่วย Preterm อย่างใกล้ชิดเพื่อลดอัตราแทรกซ้อน</p>
            </div>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4 mb-6">
            <div class="card border-t-4 border-blue">
                <div class="flex justify-between items-start">
                    <div>
                        <p class="text-sm text-gray-500 font-medium">สัดส่วนการคลอดปกติ</p>
                        <h3 class="text-2xl font-bold text-navy mt-1">55.4%</h3>
                        <p class="text-xs text-teal mt-1"><i class="fas fa-check-circle"></i> อยู่ในเกณฑ์ยอมรับได้</p>
                    </div>
                    <div class="p-2 bg-blue-100 rounded-full text-blue">
                        <i class="fas fa-baby fa-lg"></i>
                    </div>
                </div>
            </div>

            <div class="card border-t-4 border-red">
                <div class="flex justify-between items-start">
                    <div>
                        <p class="text-sm text-gray-500 font-medium">ภาระงานหลังคลอด (PP Productivity)</p>
                        <h3 class="text-2xl font-bold text-red mt-1">117.7%</h3>
                        <p class="text-xs text-red mt-1"><i class="fas fa-exclamation-circle"></i> สูงกว่าเป้าหมาย (90-110%)</p>
                    </div>
                    <div class="p-2 bg-red-100 rounded-full text-red">
                        <i class="fas fa-user-nurse fa-lg"></i>
                    </div>
                </div>
            </div>

            <div class="card border-t-4 border-teal">
                <div class="flex justify-between items-start">
                    <div>
                        <p class="text-sm text-gray-500 font-medium">อัตราการส่งต่อ (Refer Rate)</p>
                        <h3 class="text-2xl font-bold text-navy mt-1">1.24%</h3>
                        <p class="text-xs text-teal mt-1"><i class="fas fa-arrow-down"></i> ลดลงจากปีก่อน (1.56%)</p>
                    </div>
                    <div class="p-2 bg-teal-100 rounded-full text-teal">
                        <i class="fas fa-ambulance fa-lg"></i>
                    </div>
                </div>
            </div>

            <div class="card border-t-4 border-amber">
                <div class="flex justify-between items-start">
                    <div>
                        <p class="text-sm text-gray-500 font-medium">ความพึงพอใจผู้รับบริการ</p>
                        <h3 class="text-2xl font-bold text-navy mt-1">100%</h3>
                        <p class="text-xs text-gray-500 mt-1">ข้อมูล IP Voices (Sample)</p>
                    </div>
                    <div class="p-2 bg-amber-100 rounded-full text-amber">
                        <i class="fas fa-smile fa-lg"></i>
                    </div>
                </div>
            </div>
        </div>

        <div class="grid grid-cols-1 lg:grid-cols-2 gap-6 mb-6">
            <div class="card">
                <h2 class="section-title">5. Situation Overview (สัดส่วนวิธีการคลอด)</h2>
                <div class="relative h-64">
                    <canvas id="deliveryChart"></canvas>
                </div>
            </div>

            <div class="card">
                <h2 class="section-title">6. Complication & Risk Overview</h2>
                <div class="relative h-64">
                    <canvas id="riskChart"></canvas>
                </div>
                <p class="text-xs text-gray-500 mt-2 text-center">*คะแนนนี้ใช้เพื่อการฝึกวิเคราะห์และการอภิปรายเชิงบริหารเท่านั้น ไม่ใช่ค่าจริง (Training scoring 1-5)</p>
            </div>
        </div>

        <div class="grid grid-cols-1 lg:grid-cols-3 gap-6 mb-6">
            <div class="card col-span-1 lg:col-span-1">
                <h2 class="section-title">7. Operations Impact (Productivity)</h2>
                <div class="space-y-4">
                    <div>
                        <div class="flex justify-between text-sm mb-1">
                            <span class="font-medium text-gray-700">LR (ห้องคลอด)</span>
                            <span class="text-amber">82.60% (ต่ำกว่าเกณฑ์)</span>
                        </div>
                        <div class="progress-bar-bg">
                            <div class="progress-bar-fill bg-amber" style="width: 82.60%;"></div>
                        </div>
                    </div>
                    <div>
                        <div class="flex justify-between text-sm mb-1">
                            <span class="font-medium text-gray-700">PP (หลังคลอด)</span>
                            <span class="text-red font-bold">117.73% (Overload)</span>
                        </div>
                        <div class="progress-bar-bg">
                            <div class="progress-bar-fill bg-red" style="width: 100%;"></div>
                        </div>
                    </div>
                    <div>
                        <div class="flex justify-between text-sm mb-1">
                            <span class="font-medium text-gray-700">ตรวจหลังคลอดตามเกณฑ์</span>
                            <span class="text-teal">98.22% (ดีมาก)</span>
                        </div>
                        <div class="progress-bar-bg">
                            <div class="progress-bar-fill bg-teal" style="width: 98.22%;"></div>
                        </div>
                    </div>
                </div>
                <div class="mt-4 p-3 bg-lightgray rounded text-sm text-gray-700">
                    <span class="font-semibold">Impact:</span> ภาระงานเทไปที่แผนกหลังคลอดอย่างหนัก เสี่ยงต่อคุณภาพการพยาบาล
                </div>
            </div>

            <div class="card col-span-1 lg:col-span-1">
                <h2 class="section-title">8. Risk Signal / Red Flags</h2>
                <div class="space-y-3">
                    <div class="p-3 bg-red-50 red-flag rounded shadow-sm">
                        <div class="flex items-center">
                            <i class="fas fa-exclamation-circle text-red mr-2"></i>
                            <h4 class="font-bold text-red text-sm">Critical Staffing (PP)</h4>
                        </div>
                        <p class="text-xs mt-1 text-gray-600">Productivity เกิน 110% ต่อเนื่อง เสี่ยงต่ออุบัติการณ์ทางคลินิก (Human Error)</p>
                    </div>
                    <div class="p-3 bg-amber-50 amber-flag rounded shadow-sm">
                        <div class="flex items-center">
                            <i class="fas fa-exclamation-triangle text-amber mr-2"></i>
                            <h4 class="font-bold text-amber text-sm">Preterm Alert</h4>
                        </div>
                        <p class="text-xs mt-1 text-gray-600">พบการให้ยาระงับคลอดและ Refer ในราย GA < 34 wks ต้องการ NICU standby</p>
                    </div>
                </div>
            </div>

            <div class="card col-span-1 lg:col-span-1">
                <h2 class="section-title">9. Hospital Readiness</h2>
                <p class="text-xs text-gray-500 mb-3">*คะแนนเชิงบริหารสำหรับฝึกอบรม (1-5)</p>
                <div class="space-y-4">
                    <div>
                        <div class="flex justify-between text-sm mb-1">
                            <span class="font-medium text-gray-700">Medical Supplies</span>
                            <span class="text-teal">ระดับ 5/5</span>
                        </div>
                        <div class="progress-bar-bg">
                            <div class="progress-bar-fill bg-teal" style="width: 100%;"></div>
                        </div>
                    </div>
                    <div>
                        <div class="flex justify-between text-sm mb-1">
                            <span class="font-medium text-gray-700">Blood Bank Standby</span>
                            <span class="text-teal">ระดับ 4/5</span>
                        </div>
                        <div class="progress-bar-bg">
                            <div class="progress-bar-fill bg-teal" style="width: 80%;"></div>
                        </div>
                    </div>
                    <div>
                        <div class="flex justify-between text-sm mb-1">
                            <span class="font-medium text-gray-700">NICU Bed Availability</span>
                            <span class="text-amber">ระดับ 2/5</span>
                        </div>
                        <div class="progress-bar-bg">
                            <div class="progress-bar-fill bg-amber" style="width: 40%;"></div>
                        </div>
                        <p class="text-xs text-amber mt-1 text-right">เหลือเตียงว่างน้อย</p>
                    </div>
                </div>
            </div>
        </div>

        <div class="card mb-6">
            <h2 class="section-title">10. Executive Action Timeline</h2>
            <div class="flex flex-col md:flex-row gap-4">
                <div class="flex-1 bg-red-50 p-4 rounded border-t-4 border-red">
                    <h3 class="font-bold text-red"><i class="fas fa-clock mr-1"></i> 24 ชั่วโมง</h3>
                    <ul class="list-disc pl-5 mt-2 text-sm text-gray-700 space-y-1">
                        <li>สั่งการเกลี่ยพยาบาลจาก LR/OPD มาช่วย PP ชั่วคราว</li>
                        <li>ประเมินจำนวนเตียงว่าง NICU รองรับเคส Preterm</li>
                    </ul>
                </div>
                <div class="flex-1 bg-amber-50 p-4 rounded border-t-4 border-amber">
                    <h3 class="font-bold text-amber"><i class="fas fa-calendar-week mr-1"></i> 7 วัน</h3>
                    <ul class="list-disc pl-5 mt-2 text-sm text-gray-700 space-y-1">
                        <li>ประชุมทบทวนเคส Refer เพื่อหาแนวทางลดอัตราส่งต่อ</li>
                        <li>ตรวจสอบความครบถ้วนของการตรวจหลังคลอด 3 ครั้ง</li>
                    </ul>
                </div>
                <div class="flex-1 bg-teal-50 p-4 rounded border-t-4 border-teal">
                    <h3 class="font-bold text-teal"><i class="fas fa-calendar-alt mr-1"></i> 30 วัน</h3>
                    <ul class="list-disc pl-5 mt-2 text-sm text-gray-700 space-y-1">
                        <li>ปรับปรุงโครงสร้างอัตรากำลัง (Manpower Plan) ระยะยาว</li>
                        <li>วิเคราะห์งบประมาณจัดซื้ออุปกรณ์ช่วยคลอดเพิ่มเติม</li>
                    </ul>
                </div>
            </div>
        </div>

        <div class="bg-gray-100 p-4 rounded border border-gray-200 text-xs text-gray-600">
            <h4 class="font-bold mb-1 text-gray-800">11. Data Limitation & Ethics Note:</h4>
            <ul class="list-disc pl-5 space-y-1">
                <li>ข้อมูลที่แสดงอ้างอิงจากฐานข้อมูลการฝึกอบรม (ไม่มีการระบุตัวตนผู้ป่วย)</li>
                <li>บางตัวชี้วัด เช่น Hospital Readiness เป็นการจำลองคะแนน (Training Scoring) เพื่อใช้ในการอภิปรายเชิงบริหารเท่านั้น ไม่มีข้อมูลยืนยันจากแหล่งข้อมูลจริงทั้งหมด</li>
                <li>ห้ามนำข้อมูลนี้ไปใช้ในการตัดสินใจรักษาทางคลินิก (No Medical Advice/Diagnosis)</li>
            </ul>
        </div>

    </div>

    <script>
        // Set Current Date Script (Fallback if not overridden by dynamic context)
        const dateElement = document.getElementById('currentDate');
        const today = new Date();
        const options = { year: 'numeric', month: 'long', day: 'numeric' };
        // dateElement.innerText = today.toLocaleDateString('th-TH', options); // Using pre-rendered text for exact sync with context

        // 5. Situation Overview Chart (Delivery Types)
        const ctxDelivery = document.getElementById('deliveryChart').getContext('2d');
        new Chart(ctxDelivery, {
            type: 'doughnut',
            data: {
                labels: ['Normal Delivery', 'Cesarean Section (C/S)', 'อื่นๆ (Vacuum, etc.)'],
                datasets: [{
                    data: [55.4, 41.0, 3.6],
                    backgroundColor: ['#0d9488', '#f59e0b', '#6b7280'],
                    borderWidth: 0
                }]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                plugins: {
                    legend: { position: 'bottom' }
                },
                cutout: '60%'
            }
        });

        // 6. Disease Risk Comparison Chart (Complications - Mock Training Data)
        const ctxRisk = document.getElementById('riskChart').getContext('2d');
        new Chart(ctxRisk, {
            type: 'radar',
            data: {
                labels: ['PPH (ตกเลือด)', 'Preterm Labor', 'Severe Preeclampsia', 'Fetal Distress', 'Infection'],
                datasets: [{
                    label: 'ระดับความเสี่ยงปัจจุบัน (1-5)',
                    data: [3, 4, 2, 3, 1], // Training scoring 1-5
                    backgroundColor: 'rgba(239, 68, 68, 0.2)',
                    borderColor: '#ef4444',
                    pointBackgroundColor: '#ef4444',
                }, {
                    label: 'ค่าเฉลี่ยปีที่ผ่านมา (1-5)',
                    data: [2, 3, 2, 2, 2],
                    backgroundColor: 'rgba(13, 148, 136, 0.2)',
                    borderColor: '#0d9488',
                    pointBackgroundColor: '#0d9488',
                }]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                scales: {
                    r: {
                        angleLines: { display: true },
                        suggestedMin: 0,
                        suggestedMax: 5,
                        ticks: { stepSize: 1 }
                    }
                },
                plugins: {
                    legend: { position: 'bottom' }
                }
            }
        });
    </script>
</body>
</html>
