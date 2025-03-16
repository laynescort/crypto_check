<?php
// config.php
define('CRYPTOPANIC_API_KEY', '9cb3391d5a64616957da253793191224f91ba4bd');
?>

<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Crypto Analytics</title>
    <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet>
    <style>
        .active-tab { border-bottom: 3px solid #3b82f6; font-weight: 600; }
        .result-box { transition: all 0.3s ease; }
    </style>
</head>
<body class="bg-gray-100 min-h-screen">
    <div class="container mx-auto px-4 py-12 max-w-4xl">
        <!-- Header -->
        <div class="text-center mb-12">
            <h1 class="text-4xl font-bold text-blue-600 mb-4">Kripto Analiz Platformu</h1>
            <div class="flex justify-center space-x-4 mb-8">
                <button onclick="showTab('price')" class="tab-btn px-6 py-3 text-lg">Fiyat Sorgula</button>
                <button onclick="showTab('analysis')" class="tab-btn px-6 py-3 text-lg">Teknik Analiz</button>
                <button onclick="showTab('news')" class="tab-btn px-6 py-3 text-lg">Son Haberler</button>
            </div>
        </div>

        <!-- Fiyat Sorgulama -->
        <div id="price" class="tab-content bg-white p-8 rounded-xl shadow-lg mb-8">
            <form method="POST" class="space-y-4">
                <input type="text" name="coin" placeholder="Coin adı (Örnek: bitcoin)" 
                    class="w-full p-4 border-2 border-gray-200 rounded-lg focus:ring-2 focus:ring-blue-400">
                <button type="submit" name="price_action" 
                    class="bg-blue-500 hover:bg-blue-600 text-white px-8 py-3 rounded-lg font-semibold">
                    Fiyatı Görüntüle
                </button>
            </form>
            
            <?php
            if(isset($_POST['price_action'])) {
                $coin = htmlspecialchars(strtolower($_POST['coin']));
                $url = "https://api.coingecko.com/api/v3/coins/$coin";
                
                try {
                    $data = json_decode(file_get_contents($url), true);
                    
                    if(isset($data['market_data'])) {
                        $usd = number_format($data['market_data']['current_price']['usd'], 2);
                        $try = number_format($data['market_data']['current_price']['try'], 2);
                        $image = $data['image']['large'];
                        echo "
                        <div class='result-box mt-6 p-6 bg-blue-50 rounded-lg flex items-start space-x-6'>
                            <img src='$image' class='w-20 h-20 rounded-lg'>
                            <div>
                                <h3 class='text-2xl font-bold text-gray-800'>{$data['name']}</h3>
                                <p class='text-xl text-green-600 mt-2'>🇺🇸 $$usd</p>
                                <p class='text-xl text-blue-600'>🇹🇷 ₺$try</p>
                            </div>
                        </div>";
                    } else {
                        echo "<div class='mt-6 p-4 bg-red-100 text-red-700 rounded-lg'>Coin bulunamadı!</div>";
                    }
                } catch(Exception $e) {
                    echo "<div class='mt-6 p-4 bg-red-100 text-red-700 rounded-lg'>API hatası: {$e->getMessage()}</div>";
                }
            }
            ?>
        </div>

        <!-- Teknik Analiz -->
        <div id="analysis" class="tab-content bg-white p-8 rounded-xl shadow-lg mb-8 hidden">
            <form method="POST" class="space-y-4">
                <input type="text" name="analysis_coin" placeholder="Coin adı (Örnek: ethereum)" 
                    class="w-full p-4 border-2 border-gray-200 rounded-lg focus:ring-2 focus:ring-blue-400">
                <button type="submit" name="analysis_action" 
                    class="bg-purple-500 hover:bg-purple-600 text-white px-8 py-3 rounded-lg font-semibold">
                    Analiz Yap
                </button>
            </form>
            
            <?php
            if(isset($_POST['analysis_action'])) {
                $coin = htmlspecialchars(strtolower($_POST['analysis_coin']));
                $url = "https://api.coingecko.com/api/v3/coins/$coin/market_chart?vs_currency=usd&days=7";
                
                try {
                    $data = json_decode(file_get_contents($url), true);
                    $prices = array_column($data['prices'], 1);
                    
                    if(count($prices) > 1) {
                        $change = (($prices[count($prices)-1] - $prices[0]) / $prices[0]) * 100;
                        $status = $change > 0 ? '👍 Yükseliş' : '👎 Düşüş';
                        $color = $change > 0 ? 'text-green-600' : 'text-red-600';
                        
                        echo "
                        <div class='result-box mt-6 p-6 bg-gray-50 rounded-lg'>
                            <h3 class='text-xl font-semibold mb-4'>7 Günlük Analiz</h3>
                            <div class='flex items-center space-x-4'>
                                <span class='text-3xl $color'>% ".number_format($change, 2)."</span>
                                <span class='text-2xl'>$status</span>
                            </div>
                            <div class='mt-4 grid grid-cols-2 gap-4'>
                                <div>
                                    <p class='text-gray-500'>Başlangıç</p>
                                    <p class='text-lg font-semibold'>$".number_format($prices[0], 2)."</p>
                                </div>
                                <div>
                                    <p class='text-gray-500'>Son Fiyat</p>
                                    <p class='text-lg font-semibold'>$".number_format(end($prices), 2)."</p>
                                </div>
                            </div>
                        </div>";
                    }
                } catch(Exception $e) {
                    echo "<div class='mt-6 p-4 bg-red-100 text-red-700 rounded-lg'>Hata: {$e->getMessage()}</div>";
                }
            }
            ?>
        </div>

        <!-- Son Haberler -->
        <div id="news" class="tab-content bg-white p-8 rounded-xl shadow-lg hidden">
            <form method="POST" class="space-y-4">
                <input type="text" name="news_symbol" placeholder="Coin sembolü (Örnek: BTC)" 
                    class="w-full p-4 border-2 border-gray-200 rounded-lg focus:ring-2 focus:ring-blue-400">
                <button type="submit" name="news_action" 
                    class="bg-green-500 hover:bg-green-600 text-white px-8 py-3 rounded-lg font-semibold">
                    Haberleri Getir
                </button>
            </form>
            
            <?php
            if(isset($_POST['news_action'])) {
                $symbol = htmlspecialchars(strtoupper($_POST['news_symbol']));
                $url = "https://cryptopanic.com/api/v1/posts/?auth_token=".CRYPTOPANIC_API_KEY."&currencies=$symbol&kind=news";
                
                try {
                    $data = json_decode(file_get_contents($url), true);
                    
                    if(!empty($data['results'])) {
                        echo "<div class='mt-6 space-y-6'>";
                        foreach(array_slice($data['results'], 0, 3) as $news) {
                            $date = date('d.m.Y H:i', strtotime($news['created_at']));
                            echo "
                            <div class='result-box p-6 bg-gray-50 rounded-lg hover:shadow-sm'>
                                <div class='flex justify-between items-start mb-2'>
                                    <h3 class='text-lg font-semibold'>{$news['title']}</h3>
                                    <span class='text-sm text-gray-500'>$date</span>
                                </div>
                                <a href='{$news['url']}' target='_blank' 
                                    class='text-blue-500 hover:text-blue-600 inline-flex items-center'>
                                    Detayları Gör 
                                    <svg class='w-4 h-4 ml-1' fill='none' stroke='currentColor' viewBox='0 0 24 24'>
                                        <path stroke-linecap='round' stroke-linejoin='round' stroke-width='2' d='M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14'/>
                                    </svg>
                                </a>
                            </div>";
                        }
                        echo "</div>";
                    } else {
                        echo "<div class='mt-6 p-4 bg-yellow-100 text-yellow-700 rounded-lg'>Haber bulunamadı</div>";
                    }
                } catch(Exception $e) {
                    echo "<div class='mt-6 p-4 bg-red-100 text-red-700 rounded-lg'>Hata: {$e->getMessage()}</div>";
                }
            }
            ?>
        </div>
    </div>

    <script>
        function showTab(tabId) {
            // Tüm sekmeleri ve butonları resetle
            document.querySelectorAll('.tab-content').forEach(tab => tab.classList.add('hidden'));
            document.querySelectorAll('.tab-btn').forEach(btn => btn.classList.remove('active-tab'));
            
            // Seçilen sekme ve butonu aktif yap
            document.getElementById(tabId).classList.remove('hidden'));
            event.currentTarget.classList.add('active-tab'));
        }
    </script>
</body>
</html>