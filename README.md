<!doctype html>
<html lang='en'>
  <head>
    <!-- Meta Properties -->
    <meta charset='UTF-8'>
    <title>surviv.io - 2d battle royale game</title>
    <meta name="viewport" content="width=device-width, height=device-height, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0, viewport-fit=cover, user-scalable=no">
    <link rel="manifest" href="manifest.json">
    <meta name="mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-title" content="surviv.io">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <meta name="application-name" content="surviv.io">
    <meta name="description" content="Like games such as Player Unknown's Battlegrounds (PUBG), Fortnite or Apex Legends? Play this free 2d battle royale io game in your browser!">
    <meta property="og:description" content="Like games such as Player Unknown's Battlegrounds (PUBG), Fortnite or Apex Legends? Play this free 2d battle royale io game in your browser!">
    <meta name="keywords" content="survivio, surviv, 2d battle royale, io, battle royale browser game, 2d battlegrounds, battlegrounds, battleroyale, battle, royale, browser game, br, survival, game, web game, multiplayer">
    <meta property="og:type" content="website">
    <meta property="og:title" content="surviv.io">
    <meta property="og:url" content="https://surviv.io/">
    <meta property="og:site_name" content="surviv.io">
    <meta content="https://surviv.io/img/title.png" property="og:image">
    <link rel="canonical" href="http://surviv.io" />
    <link rel="apple-touch-icon-precomposed" href="img/icon_app.png">
    <link rel="icon" href="favicon.ico" type="image/x-icon">
    <!-- Global site tag (gtag.js) - Google Analytics -->
    <script>
     window.adsBlocked = false;
     window.adBlockDetected = function() { window.adsBlocked = true; }
     window.alert = function() { }
     /* Cookie consent */
     var cfg = {};
     var consented = true;
     var webview = false;
     try {
       cfg = JSON.parse(localStorage.getItem('surviv_config')) || {};
       if (cfg.cookiesConsented != undefined) { consented = cfg.cookiesConsented; }
       webview = localStorage.getItem('surviv_webview');
     } catch (e) { }
     window.cookiesConsented = consented;
     if (window.cookiesConsented) {
       document.write("<script async src='https://www.googletagmanager.com/gtag/js?id=UA-108811301-1' onerror='adBlockDetected();'>\x3C/script>");
       window.dataLayer = window.dataLayer || [];
       function gtag(){dataLayer.push(arguments);}
       gtag('js', new Date());
       gtag('config', 'UA-108811301-1', { 'anonymize_ip': true });
     }
     window.webviewDetected = new RegExp("[?&]webview=true","gi").test(window.location.href) || webview;
    </script>
    <!-- AIP -->
    <script>
     document.write("<script async src='//api.adinplay.com/libs/aiptag/pub/SRV/surviv.io/tag.min.js'>\x3C/script>");
     var aiptag = aiptag || {};
     aiptag.gdprConsent = window.cookiesConsented;
     aiptag.consented = window.cookiesConsented;
     aiptag.cmd = aiptag.cmd || [];
     aiptag.cmd.display = aiptag.cmd.display || [];
    </script>
    <!-- Fonts -->
    <link href="https://fonts.googleapis.com/css?family=Roboto+Condensed:400,700" rel="stylesheet">
  <link href="css/app.9932caca.css" rel="stylesheet"></head>
  <body>
    <div id='preroll-wrapper'>
      <div id="preroll"></div>
    </div>
    <div id="fb-root"></div>
    <canvas tabindex='1' id='cvs'></canvas>
    <div id='game-area-wrapper' style='display: none' oncontextmenu='return false;'>
      <div id='game-touch-area'></div>
      <div id='ui-game' class='click-through'>
        <div id='tablet-console'></div>
        <div id='ui-center'>
          <div id='ui-game-menu'>
            <div id='btn-game-tabs' class='btns-game-double-row'>
              <div class='btn-game-container'>
                <a id='btn-game-settings' class='btn-game-tab-select btn-game-menu btn-game-menu-selected btn-darken' data-tab='settings'></a>
                <div class='btn-double-row game-menu-icon-static settings-icon'></div>
              </div>
              <div class='btn-game-container'>
                <a id='btn-game-keybinds' class='btn-game-tab-select btn-game-menu btn-darken' data-tab='keybinds'></a>
                <div class='btn-double-row game-menu-icon-static keybind-icon'></div>
              </div>
            </div>
            <div id='ui-game-tab-settings' class='ui-game-tab'>
              <a id='btn-game-fullscreen' class='btn-fullscreen-toggle btn-game-menu btn-darken' data-l10n='game-full-screen'>Full Screen</a>
              <div id='btn-touch-styles' class='btns-game-double-row'>
                <div class='btn-game-container'>
                  <a id='btn-game-move-style' class='btn-double-row btn-game-touch-style btn-darken'></a>
                  <div class='btn-double-row game-menu-icon-toggle movement-icon'></div>
                </div>
                <div class='btn-game-container'>
                  <a id='btn-game-aim-style' class='btn-double-row btn-game-touch-style btn-darken'></a>
                  <div class='btn-double-row game-menu-icon-toggle target-icon'></div>
                </div>
              </div>
              <a id='btn-game-aim-line' class='btn-game-menu btn-darken locked-on-icon' data-l10n='game-aim-line'>Aim Line</a>
              <a id='btn-game-sound' class='btn-sound-toggle btn-game-menu btn-darken audio-on-icon' data-l10n='game-sound'>Sound</a>
              <div class="slider-container ui-slider-container">
                <p class='slider-text' data-l10n='index-master-volume'>Master Volume</p>
                <input type="range" min="0" max="100" value="100" class="slider sl-master-volume">
              </div>
              <div class="slider-container ui-slider-container">
                <p class='slider-text' data-l10n='index-sfx-volume'>SFX Volume</p>
                <input type="range" min="0" max="100" value="100" class="slider sl-sound-volume">
              </div>
              <div class="slider-container ui-slider-container">
                <p class='slider-text' data-l10n='index-music-volume'>Music Volume</p>
                <input type="range" min="0" max="100" value="100" class="slider sl-music-volume">
              </div>
              <a id='btn-game-quit' class='btn-quit btn-game-menu btn-darken' data-l10n='game-quit-game'>Quit Game</a>
            </div>
            <div id='ui-game-tab-keybinds' class='ui-game-tab'>
              <div id='ui-keybind-list' class='js-keybind-list'></div>
              <a class='js-btn-keybind-restore btn-keybind-restore btn-game-menu btn-darken' data-l10n='game-restore-defaults'>Restore Defaults</a>
            </div>
            <a id='btn-game-resume' class='btn-game-menu btn-darken' data-l10n='game-return-to-game'>Return to Game</a>
          </div>
        </div>
        <div id='big-map' class='js-ui-map-show'>
          <div id='big-map-collision'></div>
          <div id='big-map-close'></div>
        </div>
        <div id='ui-emotes' class='ui-emote-wheel'>
          <div id='ui-emote-middle' class='ui-emote-middle ui-emote-circle ui-emote-parent' data-key='middle' data-id='0'>
            <div class='ui-emote ui-emote-bg-circle'></div>
            <div class='ui-emote ui-emote-hl'></div>
            <div class='ui-emote-image ui-emote-image-large'></div>
          </div>
          <div id='ui-emote-top' class='ui-emote-top ui-emote-quarter ui-emote-parent' data-key='top' data-id='1'>
            <div class='ui-emote ui-emote-bg-quarter'></div>
            <div class='ui-emote ui-emote-hl'></div>
            <div class='ui-emote-image ui-emote-image-large'></div>
          </div>
          <div id='ui-emote-right' class='ui-emote-right ui-emote-quarter ui-emote-parent' data-key='right' data-id='2'>
            <div class='ui-emote ui-emote-bg-quarter'></div>
            <div class='ui-emote ui-emote-hl'></div>
            <div class='ui-emote-image ui-emote-image-large'></div>
          </div>
          <div id='ui-emote-bottom' class='ui-emote-bottom ui-emote-quarter ui-emote-parent' data-key='bottom' data-id='3'>
            <div class='ui-emote ui-emote-bg-quarter'></div>
            <div class='ui-emote ui-emote-hl'></div>
            <div class='ui-emote-image ui-emote-image-large'></div>
          </div>
          <div id='ui-emote-left' class='ui-emote-left ui-emote-quarter ui-emote-parent' data-key='left' data-id='4'>
            <div class='ui-emote ui-emote-bg-quarter'></div>
            <div class='ui-emote ui-emote-hl'></div>
            <div class='ui-emote-image ui-emote-image-large'></div>
          </div>
        </div>
        <div id='ui-team-pings' class='ui-emote-wheel'>
          <div id='ui-team-ping-middle' class='ui-emote-middle ui-emote-circle ui-emote-parent' data-id='0'>
            <div class='ui-emote ui-emote-bg-circle'></div>
            <div class='ui-emote ui-emote-hl'></div>
            <div class='ui-emote-image ui-emote-image-large'></div>
          </div>
          <div id='ui-team-ping-top' class='ui-emote-top ui-emote-quarter ui-emote-parent' data-id='1'>
            <div class='ui-emote ui-emote-bg-quarter'></div>
            <div class='ui-emote ui-emote-hl'></div>
            <div class='ui-emote-image ui-emote-image-large'></div>
          </div>
          <div id='ui-team-ping-right' class='ui-emote-right ui-emote-quarter ui-emote-parent' data-id='2'>
            <div class='ui-emote ui-emote-bg-quarter'></div>
            <div class='ui-emote ui-emote-hl'></div>
            <div class='ui-emote-image ui-emote-image-large'></div>
          </div>
          <div id='ui-team-ping-bottom' class='ui-emote-bottom ui-emote-quarter ui-emote-parent' data-id='3'>
            <div class='ui-emote ui-emote-bg-quarter'></div>
            <div class='ui-emote ui-emote-hl'></div>
            <div class='ui-emote-image ui-emote-image-large'></div>
          </div>
          <div id='ui-team-ping-bottom-left' class='ui-emote-bottom-left ui-emote-eighth ui-emote-parent' data-id='4'>
            <div class='ui-emote ui-emote-bg-eighth'></div>
            <div class='ui-emote ui-emote-hl'></div>
            <div class='ui-emote-image ui-emote-image-small'></div>
          </div>
          <div id='ui-team-ping-top-left' class='ui-emote-top-left ui-emote-eighth ui-emote-parent' data-id='5'>
            <div class='ui-emote ui-emote-bg-eighth'></div>
            <div class='ui-emote ui-emote-hl'></div>
            <div class='ui-emote-image ui-emote-image-small'></div>
          </div>
        </div>
        <div id='ui-team-indicators' class='js-ui-map-hidden js-desktop-ui-hud-show'>
          <div class='ui-team-indicator ui-indicator-main' data-id='0'>
            <div class='ui-team-indicator-pos ui-background-yellow'></div>
          </div>
          <div class='ui-team-indicator ui-indicator-main' data-id='1'>
            <div class='ui-team-indicator-pos ui-background-purple'></div>
          </div>
          <div class='ui-team-indicator ui-indicator-main' data-id='2'>
            <div class='ui-team-indicator-pos ui-background-cyan'></div>
          </div>
          <div class='ui-team-indicator ui-indicator-main' data-id='3'>
            <div class='ui-team-indicator-pos ui-background-orange'></div>
          </div>
          <div class='ui-team-indicator ui-indicator-main' data-id='4'>
            <div class='ui-team-indicator-pos ui-background-yellow'></div>
          </div>
          <div class='ui-team-indicator ui-indicator-ping' data-id='0'>
            <div class='ui-team-indicator-pos ui-team-indicator-image'></div>
          </div>
          <div class='ui-indicator-ping-border' data-id='0'></div>
          <div class='ui-team-indicator ui-indicator-ping' data-id='1'>
            <div class='ui-team-indicator-pos ui-team-indicator-image'></div>
          </div>
          <div class='ui-indicator-ping-border' data-id='1'></div>
          <div class='ui-team-indicator ui-indicator-ping' data-id='2'>
            <div class='ui-team-indicator-pos ui-team-indicator-image'></div>
          </div>
          <div class='ui-indicator-ping-border' data-id='2'></div>
          <div class='ui-team-indicator ui-indicator-ping' data-id='3'>
            <div class='ui-team-indicator-pos ui-team-indicator-image'></div>
          </div>
          <div class='ui-indicator-ping-border' data-id='3'></div>
          <div class='ui-team-indicator ui-indicator-ping' data-id='4'>
            <div class='ui-team-indicator-pos ui-team-indicator-image'></div>
          </div>
          <div class='ui-indicator-ping-border' data-id='4'></div>
        </div>
        <div id='ui-right-center' class='ui-right-center-desktop js-ui-map-hidden'>
          <div id='ui-medical-interactive'>
            <div id='ui-loot-bandage' class='ui-loot ui-outline-hover ui-scale-hover ui-medical tooltip'>
              <div class='tooltip-text'>
                <div class='tooltip-title' data-l10n='game-bandage'>Bandage</div>
                <div class='tooltip-description'><span data-l10n='game-bandage-tooltip'>Left-click to restore 15 health.</span></div>
              </div>
              <div class='ui-loot-count'>0</div>
              <img class='ui-loot-image' src=''></img>
            </div>
            <div id='ui-loot-healthkit' class='ui-loot ui-outline-hover ui-scale-hover ui-medical tooltip'>
              <div class='tooltip-text'>
                <div class='tooltip-title' data-l10n='game-healthkit'>Med Kit</div>
                <div class='tooltip-description'><span data-l10n='game-healthkit-tooltip'>Left-click to restore 100 health.</div>
              </div>
              <div class='ui-loot-count'>0</div>
              <img class='ui-loot-image' src=''></img>
            </div>
            <div id='ui-loot-soda' class='ui-loot ui-outline-hover ui-scale-hover ui-medical tooltip'>
              <div class='tooltip-text'>
                <div class='tooltip-title' data-l10n='game-soda'>Soda</div>
                <div class='tooltip-description'><span data-l10n='game-soda-tooltip'>Left-click to boost adrenaline by 25.</span><br><span data-l10n='game-adrenaline-tooltip'>Adrenaline restores health over time.</span></div>
              </div>
              <div class='ui-loot-count'>0</div>
              <img class='ui-loot-image' src=''></img>
            </div>
            <div id='ui-loot-painkiller' class='ui-loot ui-outline-hover ui-scale-hover ui-medical tooltip'>
              <div class='tooltip-text'>
                <div class='tooltip-title' data-l10n='game-painkiller'>Pills</div>
                <div class='tooltip-description'><span data-l10n='game-painkiller-tooltip'>Left-click to boost adrenaline by 50.</div>
              </div>
              <div class='ui-loot-count'>0</div>
              <img class='ui-loot-image' src=''></img>
            </div>
          </div>
          <div id='ui-ammo-interactive'>
            <div id='ui-loot-50AE' class='ui-outline-hover ui-ammo tooltip'>
              <div class='tooltip-text click-through'>
                <div class='tooltip-title' data-l10n='game-50AE'></div>
                <div class='tooltip-description'><span data-l10n='game-50AE-tooltip'></span></div>
              </div>
              <div class='ui-loot-count'>0</div>
              <img class='ui-loot-image' src=''></img>
              <div class='ui-loot-overlay' style='background: rgba(30,30,30,0.75)'></div>
            </div>
            <div id='ui-loot-9mm' class='ui-outline-hover ui-ammo tooltip'>
              <div class='tooltip-text click-through'>
                <div class='tooltip-title' data-l10n='game-9mm'></div>
                <div class='tooltip-description'><span data-l10n='game-9mm-tooltip'></span></div>
              </div>
              <div class='ui-loot-count'>0</div>
              <img class='ui-loot-image' src=''></img>
              <div class='ui-loot-overlay' style='background: rgba(255,153,0,0.75)'></div>
            </div>
            <div id='ui-loot-308sub' class='ui-outline-hover ui-ammo tooltip'>
              <div class='tooltip-text click-through'>
                <div class='tooltip-title' data-l10n='game-308sub'></div>
                <div class='tooltip-description'><span data-l10n='game-308sub-tooltip'></span></div>
              </div>
              <div class='ui-loot-count'>0</div>
              <img class='ui-loot-image' src=''></img>
              <div class='ui-loot-overlay' style='background: rgba(49,56,0,0.75)'></div>
            </div>
            <div id='ui-loot-12gauge' class='ui-outline-hover ui-ammo tooltip'>
              <div class='tooltip-text click-through'>
                <div class='tooltip-title' data-l10n='game-12gauge'></div>
                <div class='tooltip-description'><span data-l10n='game-12gauge-tooltip'></span></div>
              </div>
              <div class='ui-loot-count'>0</div>
              <img class='ui-loot-image' src=''></img>
              <div class='ui-loot-overlay' style='background: rgba(255,0,0,0.75)'></div>
            </div>
            <div id='ui-loot-flare' class='ui-outline-hover ui-ammo tooltip'>
              <div class='tooltip-text click-through'>
                <div class='tooltip-title' data-l10n='game-flare'></div>
                <div class='tooltip-description'><span data-l10n='game-flare-tooltip'></span></div>
              </div>
              <div class='ui-loot-count'>0</div>
              <img class='ui-loot-image' src=''></img>
              <div class='ui-loot-overlay' style='background: rgba(255,85,0,0.75)'></div>
            </div>
            <div id='ui-loot-762mm' class='ui-outline-hover ui-ammo tooltip'>
              <div class='tooltip-text click-through'>
                <div class='tooltip-title' data-l10n='game-762mm'></div>
                <div class='tooltip-description'><span data-l10n='game-762mm-tooltip'></span></div>
              </div>
              <div class='ui-loot-count'>0</div>
              <img class='ui-loot-image' src=''></img>
              <div class='ui-loot-overlay' style='background: rgba(0,102,255,0.75)'></div>
            </div>
            <div id='ui-loot-45acp' class='ui-outline-hover ui-ammo tooltip'>
              <div class='tooltip-text click-through'>
                <div class='tooltip-title' data-l10n='game-45acp'></div>
                <div class='tooltip-description'><span data-l10n='game-45acp-tooltip'></span></div>
              </div>
              <div class='ui-loot-count'>0</div>
              <img class='ui-loot-image' src=''></img>
              <div class='ui-loot-overlay' style='background: rgba(121,0,255,0.75)'></div>
            </div>
            <div id='ui-loot-556mm' class='ui-outline-hover ui-ammo tooltip'>
              <div class='tooltip-text click-through'>
                <div class='tooltip-title' data-l10n='game-556mm'></div>
                <div class='tooltip-description'><span data-l10n='game-556mm-tooltip'></span></div>
              </div>
              <div class='ui-loot-count'>0</div>
              <img class='ui-loot-image' src=''></img>
              <div class='ui-loot-overlay' style='background: rgba(3,123,0,0.75)'></div>
            </div>
          </div>
          <div id='ui-emote-button'></div>
        </div>
        <div id='ui-top-left' class='js-ui-hud-show click-through'>
          <div id='ui-team' class='js-ui-mobile-map-hidden'>
            <div class='ui-team-member ui-bg-standard' data-id='0'>
              <div class='ui-team-member-name'></div>
              <div class='ui-team-member-color ui-background-yellow'></div>
              <div class='ui-team-member-status'></div>
              <div class='ui-team-member-health'>
                <div class='ui-bar-inner ui-health-actual'></div>
              </div>
            </div>
            <div class='ui-team-member ui-bg-standard' data-id='1'>
              <div class='ui-team-member-name'></div>
              <div class='ui-team-member-color ui-background-purple'></div>
              <div class='ui-team-member-status'></div>
              <div class='ui-team-member-health'>
                <div class='ui-bar-inner ui-health-actual'></div>
              </div>
            </div>
            <div class='ui-team-member ui-bg-standard' data-id='2'>
              <div class='ui-team-member-name'></div>
              <div class='ui-team-member-color ui-background-cyan'></div>
              <div class='ui-team-member-status'></div>
              <div class='ui-team-member-health'>
                <div class='ui-bar-inner ui-health-actual'></div>
              </div>
            </div>
            <div class='ui-team-member ui-bg-standard' data-id='3'>
              <div class='ui-team-member-name'></div>
              <div class='ui-team-member-color ui-background-orange'></div>
              <div class='ui-team-member-status'></div>
              <div class='ui-team-member-health'>
                <div class='ui-bar-inner ui-health-actual'></div>
              </div>
            </div>
          </div>
        </div>
        <div id='ui-map-wrapper' class='ui-map-wrapper-desktop click-through'>
          <div id='ui-map-container'>
            <div id='ui-map-info' class='js-ui-map-hidden js-ui-hud-show'>
              <div id='ui-gas-icon' class='gas-icon'></div>
              <div id='ui-gas-timer'></div>
            </div>
            <div id='ui-spec-counter' class='js-ui-map-hidden js-ui-hud-show'>
              <div id='ui-spec-counter-icon'></div>
              <div id='ui-spec-counter-number'></div>
            </div>
            <div id='ui-settings-container-desktop' class='js-ui-desktop-map-hidden'>
              <div id='ui-map-expand-desktop' class='ui-map-expand ui-settings-button'>
                <img id='mag-glass-white' src=''></img>
              </div>
              <div id='ui-map-minimize' class='ui-settings-button js-ui-map-hidden'>
                <img id='ui-minimize-img' src=''></img>
              </div>
            </div>
            <div id='ui-settings-container-mobile' class='js-ui-mobile-map-hidden'>
              <div id='ui-alive-info'>
                <div id='ui-alive-icon' class='ui-map-icon alive-icon'></div>
                <div id='ui-map-counter-default' class='js-ui-players-alive'>0</div>
                <div id='ui-map-counter-faction'>
                  <span class='ui-players-alive-red js-ui-players-alive-red'>0</span>:<span class='ui-players-alive-blue js-ui-players-alive-blue'>0</span>
                </div>
              </div>
              <div id='ui-map-expand-mobile' class='ui-map-expand ui-settings-button'></div>
              <div id='ui-menu-display' class='ui-settings-button prop-event'></div>
            </div>
          </div>
        </div>
        <div id='ui-killfeed-wrapper'>
          <div id='ui-killfeed' class='js-ui-map-hidden js-ui-hud-show'>
            <div id='ui-killfeed-contents'></div>
          </div>
        </div>
        <div id='ui-leaderboard-wrapper'>
          <div id='ui-leaderboard' class='js-ui-hud-show'>
            <div id='ui-leaderboard-alive'>
              <span class='ui-players-alive js-ui-players-alive'>0</span>
            </div>
            <div id='ui-leaderboard-alive-faction'>
              <span class='ui-players-alive-red js-ui-players-alive-red'>0</span>
              <span class='ui-players-alive-blue js-ui-players-alive-blue'>0</span>
            </div>
            <div class='ui-leaderboard-header' data-l10n='game-alive'>Alive</div>
          </div>
          <div id='ui-kill-counter-wrapper' class='js-ui-map-show'>
            <div id='ui-kill-counter'>
              <span class='ui-player-kills js-ui-player-kills'>0</span>
            </div>
            <div class='ui-kill-counter-header' data-l10n='game-kills'>Kills</div>
          </div>
        </div>
        <div id='ui-top-center-scopes-wrapper'>
          <div id='ui-top-center-scopes' class='click-through js-ui-map-hidden'>
            <div id='ui-scope-1xscope' class='ui-zoom'>
              <div class='ui-zoom-text'>
                <div class='ui-zoom-level'>1<span class='ui-zoom-append'>x</span></div>
              </div>
            </div>
            <div id='ui-scope-2xscope' class='ui-zoom ui-outline-hover'>
              <div class='ui-zoom-text'>
                <div class='ui-zoom-level'>2<span class='ui-zoom-append'>x</span></div>
              </div>
            </div>
            <div id='ui-scope-4xscope' class='ui-zoom ui-outline-hover'>
              <div class='ui-zoom-text'>
                <div class='ui-zoom-level'>4<span class='ui-zoom-append'>x</span></div>
              </div>
            </div>
            <div id='ui-scope-8xscope' class='ui-zoom ui-outline-hover'>
              <div class='ui-zoom-text'>
                <div class='ui-zoom-level'>8<span class='ui-zoom-append'>x</span></div>
              </div>
            </div>
            <div id='ui-scope-15xscope' class='ui-zoom ui-outline-hover'>
              <div class='ui-zoom-text'>
                <div class='ui-zoom-level'>15<span class='ui-zoom-append'>x</span></div>
              </div>
            </div>
          </div>
        </div>
        <div id='ui-top-center' class='js-ui-map-hidden js-ui-hud-show click-through'>
          <div id='ui-waiting-text' class='top-center-text'><span data-l10n='game-waiting-for-players'>Waiting for players</span>...</div>
          <div id='ui-spectate-text' class='top-center-text ui-spectate-mode'>
            <div class='spectate-text spectate-desc' data-l10n='game-spectating'>Spectating</div>
            <div id='spectate-player' class='spectate-text'></div>
          </div>
        </div>
        <div id='ui-upper-center' class='click-through'>
          <div id='ui-announcement'></div>
        </div>
        <div id='ui-lower-center' class='js-ui-map-hidden js-ui-hud-show click-through'>
          <div id='ui-interaction'>
            <div id='ui-interaction-press'></div>
            <div id='ui-interaction-outer'>
              <div id='ui-interaction-description'></div>
            </div>
          </div>
        </div>
        <div id='ui-bottom-center-2' class='click-through'>
          <div id='ui-pickup-message'>Not Enough Space!</div>
        </div>
        <div id='ui-equipped-ammo-wrapper' class='js-ui-map-hidden js-ui-hud-show'>
          <div id='ui-equipped-ammo'>
            <div id='ui-bullet-counter'>
              <div id='ui-current-clip'>0</div>
              <div id='ui-remaining-ammo'>0</div>
              <div id='ui-reload-button-container'>
                <div id='ui-reload-button'></div>
              </div>
            </div>
          </div>
        </div>
        <div id='ui-bottom-center-0' class='click-through js-ui-map-hidden js-ui-hud-show'>
          <div id='ui-boost-counter'>
            <div class='ui-boost-base' id='ui-boost-counter-0'>
              <div class='ui-bar-inner'></div>
            </div>
            <div class='ui-boost-base' id='ui-boost-counter-1'>
              <div class='ui-bar-inner'></div>
            </div>
            <div class='ui-boost-base' id='ui-boost-counter-2'>
              <div class='ui-bar-inner'></div>
            </div>
            <div class='ui-boost-base' id='ui-boost-counter-3'>
              <div class='ui-bar-inner'></div>
            </div>
          </div>
          <div id='ui-health-counter'>
            <div id='ui-health-flair-left' class='ui-health-flair'></div>
            <div id='ui-health-flair-right' class='ui-health-flair'></div>
            <div id='ui-health-container'>
              <div class='ui-bar-inner' id='ui-health-actual'></div>
              <div class='ui-bar-inner' id='ui-health-depleted'></div>
            </div>
          </div>
        </div>
        <div id='ui-bottom-center-left' class='js-ui-map-hidden'>
          <div id='ui-perk-0' class='ui-armor-counter tooltip-perk'>
            <div class='tooltip-text'>
              <div class='tooltip-title'></div>
              <div class='tooltip-desc'></div>
            </div>
            <img class='ui-armor-image ui-loot-image' src=''></img>
          </div>
          <div id='ui-perk-1' class='ui-armor-counter tooltip-perk'>
            <div class='tooltip-text'>
              <div class='tooltip-title'></div>
              <div class='tooltip-desc'></div>
            </div>
            <img class='ui-armor-image ui-loot-image' src=''></img>
          </div>
        </div>
        <div id='ui-bottom-center-right' class='js-ui-map-hidden'>
          <div id='ui-armor-helmet' class='ui-armor-counter ui-outline-hover'>
            <div class='ui-armor-counter-inner'></div>
            <div class='ui-armor-level'></div>
            <img class='ui-armor-image ui-loot-image' src=''></img>
          </div>
          <div id='ui-armor-chest' class='ui-armor-counter ui-outline-hover'>
            <div class='ui-armor-counter-inner'></div>
            <div class='ui-armor-level'></div>
            <img class='ui-armor-image ui-loot-image' src=''></img>
          </div>
          <div id='ui-armor-backpack' class='ui-armor-counter'>
            <div class='ui-armor-counter-inner'></div>
            <div class='ui-armor-level'></div>
            <img class='ui-armor-image ui-loot-image' src=''></img>
          </div>
        </div>
        <div id='ui-bottom-right' class='js-ui-map-hidden'>
          <div id='ui-weapon-container'>
            <div class='ui-weapon-info'>
              <div class='ui-weapon-switch ui-outline-hover' id='ui-weapon-id-1' data-slot='1'>
                <div class='ui-weapon-name'></div>
                <div class='ui-weapon-number'>1</div>
                <img class='ui-weapon-image' src=''></img>
              </div>
            </div>
            <div class='ui-weapon-info'>
              <div class='ui-weapon-switch ui-outline-hover' id='ui-weapon-id-2' data-slot='2'>
                <div class='ui-weapon-name'></div>
                <div class='ui-weapon-number'>2</div>
                <img class='ui-weapon-image' src=''></img>
              </div>
            </div>
            <div class='ui-weapon-info'>
              <div class='ui-weapon-switch ui-outline-hover' id='ui-weapon-id-3'>
                <div class='ui-weapon-name'></div>
                <div class='ui-weapon-number'>3</div>
                <img class='ui-weapon-image' src=''></img>
              </div>
            </div>
            <div class='ui-weapon-info'>
              <div class='ui-weapon-switch ui-outline-hover' id='ui-weapon-id-4'>
                <div class='ui-weapon-name'></div>
                <div class='ui-weapon-number'>4</div>
                <div class='ui-weapon-exp ui-weapon-ammo-counter'>0</div>
                <img class='ui-weapon-image' src=''></img>
              </div>
            </div>
          </div>
        </div>
        <div id='ui-spectate-options-wrapper'>
          <div id='ui-spectate-options' class='ui-spectate-mode js-ui-hud-show click-through'>
            <div id='ui-spectate-buttons' class='ui-bg-standard'>
              <a class='menu-option btn-darken' id='btn-spectate-next-player' data-l10n='game-next-teammate'>Next Teammate</a>
              <a class='menu-option btn-darken' id='btn-spectate-prev-player' data-l10n='game-previous-teammate'>Previous Teammate</a>
              <a class='menu-option btn-darken' id='btn-spectate-view-stats' data-l10n='game-view-match-stats'>View Match Stats</a>
              <a class='menu-option btn-darken btn-quit' id='btn-spectate-quit' data-l10n='game-leave-game'>Leave Game</a>
            </div>
            <div id='ui-spectate-stats' class='ui-bg-standard'>
              <div id='ui-spectate-stats-header' data-l10n='game-your-results'>Your Results</div>
              <table id='ui-spectate-stats-table'>
                <tbody id='ui-spectate-stats-data'>
                </tbody>
              </table>
            </div>
          </div>
        </div>
        <div id='ui-bottom-center-1' class='click-through'>
          <div id='ui-kills'>
            <div id='ui-kill-text'></div>
            <div id='ui-kill-count'></div>
          </div>
        </div>
      </div>
      <div id='ui-stats'>
        <div id='ui-stats-bg'></div>
        <div id='ui-stats-contents'>
          <div id='ui-stats-contents-inner'>
            <div id='ui-stats-header'></div>
            <div id='ui-stats-info-box'></div>
            <div id='ui-stats-options'></div>
            <div id='ui-stats-logo'></div>
          </div>
          <div id='ui-stats-ad-container-desktop' class='ui-stats-ad-container'>
            <div id='surviv-io_300x250_2'></div>
          </div>
          <div id='ui-stats-ad-container-mobile' class='ui-stats-ad-container'>
            <div id='surviv-io_300x250_mobile_2'></div>
          </div>
        </div>
      </div>
      <div class='ui-stats-adblock surviv-shirts'>
        <a class='surviv-shirts-link' href='https://www.amazon.com/s?rh=n%3A7141123011%2Cp_4%3Asurviv.io&ref=w_bl_sl_s_ap_web_7141123011' target="_blank"></a>
      </div>
      <div class='ui-stats-adblock adblock-plea'>
        <span>Please consider supporting us by disabling your adblocker.</span>
      </div>
      
    </div>
    <div id='start-menu-wrapper'>
      <div id='safari-margin'></div>
      <div id='background'>
        <div id='start-overlay'></div>
      </div>
      <div id='start-main'>
        <div id='start-top-left'>
          <div id='btn-hamburger' class='icon-hamburger'></div>
          <div id='start-top-left-desktop'>
            <div id='featured-streamers'>
              <div class='streaming-header'>
                <div id='streaming-header-title' data-l10n='index-streaming-live'>Streaming Live!</div>
                <div id='streaming-icon'></div>
              </div>
              <div class='streamer-list'></div>
              <div id='featured-streamer-template'>
                <a href='' target='_blank' class='btn-streamer btn-darken'></a>
              </div>
            </div>
            <div id='featured-youtuber'>
              <div class='youtube-header'>
                <div id='youtube-header-title' data-l10n='index-featured-youtuber'>Featured YouTuber</div>
              </div>
              <a href='' target='_blank' class='btn-youtuber btn-darken'></a>
            </div>
          </div>
        </div>
        <!-- Accounts Modals -->
        <div id='modal-account-name-change' class='modal modal-account'>
          <div class='modal-content modal-close'>
            <div class='modal-header modal-header-name'>
              <span class='close close-corner'></span>
              <h2 id='modal-account-name-title' data-l10n='index-create-account'>Create Account</h2>
            </div>
            <div class='modal-body modal-body-name'>
              <div class='modal-settings-item'>
                <p id='modal-account-name-desc' class='modal-body-text' data-l10n='index-set-account-name'>Set your account name:</p>
                <div id='modal-body-warning'></div>
                <input type='text' class='menu-option player-name-input' tabindex='0' placeholder='Enter name' id='modal-account-name-input' maxlength='16' />
              </div>
            </div>
            <div class='modal-footer modal-footer-name modal-footer-round'>
              <h3 id='modal-account-name-finish' class='finish' data-l10n='index-finish'>Finish</h3>
            </div>
          </div>
        </div>
        <div id='modal-account-reset-stats' class='modal modal-account'>
          <div class='modal-content modal-close'>
            <div class='modal-header modal-header-reset-stats'>
              <span class='close close-corner'></span>
              <h2 id='modal-account-name-title' data-l10n='index-reset-stats'>Reset Stats</h2>
            </div>
            <div class='modal-body modal-body-reset-stats'>
              <div class='modal-settings-item'>
                <p id='modal-account-reset-stats-desc' class='modal-body-text' data-l10n='index-reset-stats-desc'>Enter "RESET STATS" to reset your stats:</p>
                <input type='text' class='menu-option player-name-input' tabindex='0' placeholder='' id='modal-account-reset-stats-input' maxlength='16' />
              </div>
            </div>
            <div class='modal-footer modal-footer-reset-stats modal-footer-round'>
              <h3 id='modal-account-reset-stats-finish' class='finish' data-l10n='index-confirm'>Confirm</h3>
            </div>
          </div>
        </div>

        <!-- Accounts Mobile -->
        <div id='modal-mobile-account' class='modal'>
          <div class='modal-content modal-close'>
            <div class='modal-header'>
              <span class='close close-corner'></span>
              <h2 data-l10n='index-account' data-l10n='index-account'>Account</h2>
            </div>
            <div id='modal-mobile-account-body'>
              <div class='account-buttons-settings account-buttons-wrapper account-block-arrow modal-close'>
                <div class='account-buttons'>
                  <div class='account-stats-link btn-player-stats-link menu-option btn-darken btn-standard ' data-l10n='index-my-stats'>My Stats</div>
                  <div class='btn-account-link btn-account-turq menu-option btn-darken btn-standard' data-l10n='index-link-account'>Link Account</div>
                  <div class='btn-account-change-name btn-account-turq menu-option btn-darken btn-standard' data-l10n='index-change-account-name'>Change Account Name</div>
                  <div class='btn-account-reset-stats btn-account-turq menu-option btn-darken btn-standard' data-l10n='index-reset-stats'>Reset Stats</div>
                  <div class='btn-account-logout btn-account-grey menu-option btn-darken btn-standard' data-l10n='index-log-out'>Log Out</div>
                </div>
              </div>
              <div id='account-login-options-mobile' class='account-buttons-link-account account-buttons-wrapper account-block-arrow modal-close'>
                <div class='login-options-content'></div>
              </div>
            </div>
          </div>
        </div>

        <!-- Accounts -->
        <div id='start-top-right'>
          <div class='account-block'>
            <div class='account-details-top'>
              <div class="account-details-top-buttons">
                <div class="account-details-button-wrapper account-details-button-loadout menu-option btn-darken-alt">
                  <div class='account-details-button'>
                    <div id='loadout-alert-main' class='account-alert-main account-alert'></div>
                    <div class='account-link account-loadout-link'>
                      <span data-l10n='index-loadout'>Loadout</span>
                    </div>
                  </div>
                </div>
                <div class="account-details-button-wrapper account-details-link-out menu-option btn-darken hide-on-mobile">
                  <div class='account-details-button'>
                    <div class='account-link account-stats-link'><span data-l10n='index-my-stats'>My Stats</span></div>
                  </div>
                </div>
                <div class="account-details-button-wrapper account-details-link-out menu-option btn-darken hide-on-mobile">
                  <div class='account-details-button'>
                    <div class='account-link account-leaderboard-link'><span data-l10n='index-leaderboards'>Leaderboards</span></div>
                  </div>
                </div>
              </div>
            </div>
            <div class='account-overview'>
              <div class="account-details-user account-details-block">
                <div class="account-details">
                  <div class="account-avatar"></div>
                  <div id="account-login" class="account-player-name account-name account-name-user" data-l10n='index-log-in-desc'>Log In / Create Account</div>
                  <div id="account-player-name" class="account-player-name account-name account-name-user" style="display:none"></div>
                  <div class="account-loading-container">
                    <div class="account-loading"></div>
                  </div>
                </div>
              </div>
            </div>
            <div class='account-buttons-settings account-buttons-wrapper account-block-arrow modal-close hide-on-mobile'>
              <div class='account-buttons'>
                <div class='btn-account-link btn-account-turq menu-option btn-darken btn-standard' data-l10n='index-link-account'>Link Account</div>
                <div class='btn-account-change-name btn-account-turq menu-option btn-darken btn-standard' data-l10n='index-change-account-name'>Change Account Name</div>
                <div class='btn-account-reset-stats btn-account-turq menu-option btn-darken btn-standard' data-l10n='index-reset-stats'>Reset Stats</div>
                <div class='btn-account-logout btn-account-grey menu-option btn-darken btn-standard' data-l10n='index-log-out'>Log Out</div>
              </div>
            </div>
            <div id='account-login-options' class='account-buttons-link-account account-buttons-wrapper account-block-arrow modal-close hide-on-mobile'>
              <div class='login-options-content'></div>
            </div>
          </div>
        </div>

        <div id='start-main-center'>
          <div id='start-row-header'>
            <div id='server-warning'></div>
          </div>
          <div id='start-row-top'>
            <div id='start-rotate-reminder' class='menu-column menu-block'>
              <span>Rotate to landscape for a better experience.</span>
            </div>
            <div id='ad-block-left' class='menu-column'>
              <div class='surviv-shirts'>
                <a href='https://www.amazon.com/s?rh=n%3A7141123011%2Cp_4%3Asurviv.io&ref=w_bl_sl_s_ap_web_7141123011' target="_blank"></a>
              </div>
              <div class='adblock-plea'>
                <span>Please consider supporting us by disabling your adblocker.</span>
              </div>
              <div class='ad-block-med-rect' id='surviv-io_300x250'>
              </div>
              <script>
               if (!window.webviewDetected) {
                 aiptag.cmd.display.push(function() { aipDisplayTag.display('surviv-io_300x250'); });
               }
              </script>
            </div>
            <div id='start-menu' class='menu-column menu-block'>
              <div class='play-loading-outer'>
                <div class='play-loading-inner'>
                  <div class='play-loading-spinner'></div>
                </div>
              </div>
              <div class='play-button-container'>
                <div id='player-options'>
                  <input type='text' class='menu-option player-name-input' tabindex='0' placeholder='Enter your name here' id='player-name-input-solo' maxlength='16' />
                  <a class='btn-darken menu-option player-options-btn' id='btn-customize'></a>
                </div>
                <select id='server-select-main' class='server-select menu-option btn-hollow btn-hollow-selected'>
                  <optgroup id='server-opts' label='Region' data-l10n='index-region'>
                    <option value='na' data-label='North America' data-l10n='index-north-america'>North America</option>
                    <option value='sa' data-label='South America' data-l10n='index-south-america'>South America</option>
                    <option value='eu' data-label='Europe' data-l10n='index-europe'>Europe</option>
                    <option value='as' data-label='Asia' data-l10n='index-asia'>Asia</option>
                    <option value='kr' data-label='Korea' data-l10n='index-korea'>South Korea</option>
                  </optgroup>
                </select>
                <a class='btn-green btn-darken menu-option' id='btn-start-mode-0' data-label='Play Solo' data-l10n='index-play-solo'>Play Solo</a>
                <div id='btns-quick-start'>
                  <a class='btn-green btn-darken menu-option' id='btn-start-mode-1' data-label='Play Duo' data-l10n='index-play-duo'>Play Duo</a>
                  <a class='btn-green btn-darken menu-option' id='btn-start-mode-2' data-label='Play Squad' data-l10n='index-play-squad'>Play Squad</a>
                </div>
                <div class='btns-double-row'>
                  <a class='btn-darken menu-option btn-team-option' id='btn-join-team' data-l10n='index-join-team'>Join Team</a>
                  <a class='btn-darken menu-option btn-team-option' id='btn-create-team' data-l10n='index-create-team'>Create Team</a>
                </div>
                <div id='btn-help' class='menu-option btn-darken' data-l10n='index-how-to-play'>How to Play</div>
                <div id='start-help'>
                  <h1 data-l10n='index-controls'>Controls</h1>
                  <p><span class='help-action' data-l10n='index-movement'></span>: <span class='help-control' data-l10n='index-movement-ctrl'></span></p>
                  <p><span class='help-action' data-l10n='index-aim'></span>: <span class='help-control' data-l10n='index-aim-ctrl'></span></p>
                  <p><span class='help-action' data-l10n='index-punch'></span>/<span class='help-action' data-l10n='index-shoot'></span>: <span class='help-control' data-l10n='index-shoot-ctrl'></span></p>
                  <p><span class='help-action' data-l10n='index-change-weapons'></span>: <span class='help-control' data-l10n='index-change-weapons-ctrl'></span></p>
                  <p class='hide-on-mobile'><span class='help-action' data-l10n='index-stow-weapons'></span>: <span class='help-control' data-l10n='index-stow-weapons-ctrl'></span></p>
                  <p class='hide-on-mobile'><span class='help-action' data-l10n='index-swap-weapons'></span>: <span class='help-control' data-l10n='index-swap-weapons-ctrl'></span></p>
                  <p class='hide-on-mobile'><span class='help-action' data-l10n='index-swap-weapon-slots'></span>: <span class='help-control' data-l10n='index-swap-weapon-slots-ctrl'></span></p>
                  <p><span class='help-action' data-l10n='index-reload'></span>: <span class='help-control' data-l10n='index-reload-ctrl'></span></p>
                  <p><span class='help-action' data-l10n='index-scope-zoom'></span>: <span class='help-control' data-l10n='index-scope-zoom-ctrl'></span></p>
                  <p><span class='help-action' data-l10n='index-pickup'></span>/<span class='help-action' data-l10n='index-loot'></span>/<span class='help-action' data-l10n='index-revive'></span>: <span class='help-control' data-l10n='index-pickup-ctrl'></span></p>
                  <p><span class='help-action' data-l10n='index-use-medical'></span>: <span class='help-control' data-l10n='index-use-medical-ctrl'></span></p>
                  <p><span class='help-action' data-l10n='index-drop-item'></span>: <span class='help-control' data-l10n='index-drop-item-ctrl'></span></p>
                  <p><span class='help-action' data-l10n='index-cancel-action'></span>: <span class='help-control' data-l10n='index-cancel-action-ctrl'></span></p>
                  <p><span class='help-action' data-l10n='index-view-map'></span>: <span class='help-control' data-l10n='index-view-map-ctrl'></span></p>
                  <p class='hide-on-mobile'><span class='help-action' data-l10n='index-toggle-minimap'></span>: <span class='help-control' data-l10n='index-toggle-minimap-ctrl'></span></p>
                  <p><span class='help-action' data-l10n='index-use-ping'></span>: <span class='help-control' data-l10n='index-use-ping-ctrl'></span></p>
                  <p><span class='help-action' data-l10n='index-use-emote'></span>: <span class='help-control' data-l10n='index-use-emote-ctrl'></span></p>
                  <h1 data-l10n='index-how-to-play'>How to Play</h1>
                  <p data-l10n='index-tips-1-desc'>The goal of surviv.io is to be the last player standing. You only live once per game - there is no respawn!</p>
                  <h1 data-l10n='index-tips-2'>2D PUBG</h1>
                  <p data-l10n='index-tips-2-desc'>If you've played other battle royale games like PUBG, Fortnite or H1Z1, then you're already halfway there! Think of surviv.io as 2D PUBG (with slightly less desync and more chicken).</p>
                  <h1 data-l10n='index-tips-3'>Loot and Kill</h1>
                  <p data-l10n='index-tips-3-desc'>You'll begin the game with no items other than a simple backpack. Move around the map to find loot: weapons, ammo, scopes, and medical items. Eliminate other players and you can take their loot!</p>
                  <h1 data-l10n='index-tips-4'>Red = Bad!</h1>
                  <p data-l10n='index-tips-4-desc'>Players aren't the only thing that can hurt you. The deadly red zone will move in from the sides of the map and deal increasingly greater damage if you stand in it. Keep an eye on the map and stay safe.</p>
                </div>
              </div>
            </div>
            <div id='team-menu' class='menu-column menu-block'>
              <div class='play-loading-outer'>
                <div class='play-loading-inner'>
                  <div class='play-loading-spinner'></div>
                </div>
              </div>
              <div class='play-button-container'>
                <a class='btn-darken menu-option' id='btn-team-leave' data-l10n='index-leave-team'>Leave Team</a>
                <div id='team-menu-connecting'>
                  <div class='ui-spinner'></div>
                  <div class='team-menu-connecting-text' id='team-menu-joining-text'><span data-l10n='index-joining-team'>Joining team</span> ...</div>
                  <div class='team-menu-connecting-text' id='team-menu-creating-text'><span data-l10n='index-creating-team'>Creating team</span> ...</div>
                </div>
                <div id='team-menu-contents'>
                  <div id='team-desc'>
                    <div id='team-desc-text'><span id='invite-link-text' data-l10n='index-invite-link'>Invite link</span>: <span id='team-url'></span>
                    </div>
                    <a id='team-copy-url' class='copy-item btn-darken'></a>
                    <a id='team-hide-url' class='hide-item btn-darken'></a>
                    <div id='team-code-text'><span id='invite-code-text' data-l10n='index-invite-code'>Invite code</span>: <span id='team-code'></span></div>
                  </div>
                  <div id='team-menu-columns'>
                    <div id='team-menu-members' class='team-menu-block'>
                      <div id='team-menu-member-list'></div>
                    </div>
                    <div id='team-menu-options' class='team-menu-block'>
                      <select id='team-server-select' class='btn-hollow btn-hollow-selected server-select menu-option'>
                        <optgroup id='team-server-opts' label='Region'>
                          <option value='na' data-label='North America' data-l10n='index-north-america'>North America</option>
                          <option value='sa' data-label='South America' data-l10n='index-south-america'>South America</option>
                          <option value='eu' data-label='Europe' data-l10n='index-europe'>Europe</option>
                          <option value='as' data-label='Asia' data-l10n='index-asia'>Asia</option>
                          <option value='kr' data-label='Korea' data-l10n='index-korea'>South Korea</option>
                        </optgroup>
                      </select>
                      <div class='team-menu-options-buttons'>
                        <a class='btn-hollow btn-hollow-selected btn-darken team-menu-option btn-team-queue' id='btn-team-queue-mode-1' data-l10n='index-duo'>Duo</a>
                        <a class='btn-hollow btn-hollow-selected btn-darken team-menu-option btn-team-queue' id='btn-team-queue-mode-2' data-l10n='index-squad'>Squad</a>
                      </div>
                      <div class='team-menu-options-buttons'>
                        <a class='btn-hollow btn-hollow-selected btn-darken team-menu-option btn-team-fill' id='btn-team-fill-auto' data-l10n='index-auto-fill'>Auto Fill</a>
                        <a class='btn-hollow btn-darken team-menu-option btn-team-fill' id='btn-team-fill-none' data-l10n='index-no-fill'>No Fill</a>
                      </div>
                      <div id='team-menu-options-start'>
                        <a class='btn-green btn-darken menu-option' id='btn-start-team' data-label='Play' data-l10n='index-play'>Play</a>
                        <div id='msg-wait-reason'></div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <div id='team-mobile-link' class='menu-column menu-block'>
              <div id='team-mobile-link-desc' class='team-mobile-link-text' data-l10n='index-join-team-help'>Got a team link or code? Paste it here:</div>
              <div id='team-mobile-link-warning' class='team-mobile-link-text'>Invalid link!</div>
              <input type='text' class='menu-option' contenteditable="false" tabindex='0' autofocus placeholder='Paste team link or enter code here' id='team-link-input' />
              <a class='btn-darken menu-option btn-team-option' id='btn-team-mobile-link-join' data-l10n='index-join-team'>Join Team</a>
              <a class='btn-darken menu-option' id='btn-team-mobile-link-leave' data-l10n='index-back-to-main'>Back to Main Menu</a>
            </div>
            <div id='right-column' class='menu-column'>
              <div id='news-block' class='menu-block'>
                <div id='news'>
                  <h3>What's New!</h3>
                  <small>August 17, 2019</small>
                  <p><strong>Get a loadout</strong></p>
                  <p>Things are about to get personal(ized) on the Island. Introducing <span class='highlight'>loadouts</span>!</p>
                  <p>Loadouts are an extension/upgrade of the emote customization system. It can be accessed through the old emote customization button, or through the new "Loadout" option in the top right corner. You must be logged in to access loadouts.</p>
                  <p>To the existing emote and player icon categories, we've added outfit skin and crosshair customization categories. Your loadout preferences are tied to your account - no more having to remake your emote setups!</p>
                  <p>This is just phase one of the loadouts rollout. We plan to add more categories, and of course, a lot more items! Let us know what you think on our <a href="https://discord.gg/survivio" target="_blank">Discord server</a>.</p>
                  <small>August 14, 2019</small>
                  <p><strong>Buffet closed</strong></p>
                  <p>PARMA scientists are confident the next game mode will have no leaky grass patches ... or more of them!</p>
                  <small>August 9, 2019</small>
                  <p><strong>All you can shoot</strong></p>
                  <p>Desert air returns once more to the Island ... but rumor tells of a curious grass sprouting from the sands.</p>
                  <p>An Initiative experiment gone awry? A portent of things to come? What madness is this?</p>
                  <small>August 1, 2019</small>
                  <p><strong>Au gratin</strong></p>
                  <p>Game modes will keep on rotating regularly through the end of summer, but we're also back to work on some exciting new features!</p>
                  <p>We're targeting mid-August for a small feature update, and early-to-mid September for a major content update.</p>
                </div>
              </div>
              <div id='social-share-block-wrapper'>
                <div id='social-share-block' class='menu-block'>
                  <div class='btn-social-wrapper'>
                    <a href='https://facebook.com/surviviogame' target='_blank' class='btn-social btn-darken btn-facebook'></a>
                    <a href='https://twitter.com/survivio' target='_blank' class='btn-social btn-darken btn-twitter'></a>
                    <a href='https://www.instagram.com/surviviogame/' target='_blank' class='btn-social btn-darken btn-instagram'></a>
                    <a href='https://discord.gg/survivio' target='_blank' class='btn-social btn-darken btn-discord'></a>
                    <a href='https://www.youtube.com/c/survivio?sub_confirmation=1' target='_blank' class='btn-social btn-darken btn-youtube'></a>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class='ad-block-leaderboard-bottom' id='surviv-io_728x90'></div>
          <script>
           if (!window.webviewDetected) {
             aiptag.cmd.display.push(function() { aipDisplayTag.display('surviv-io_728x90'); });
           }
          </script>
        </div>
        <div id='start-bottom-left'>
          <div class='hide-on-mobile'>
            <a href='https://play.google.com/store/apps/details?id=io.surviv.surviv_io_mobile' target='_blank' class='btn-download-android btn-download-app btn-darken'></a>
          </div>
          <div class='hide-on-mobile'>
            <a href='https://itunes.apple.com/us/app/surviv-io/id1401727934?ls=1&mt=8' target='_blank' class='btn-download-ios btn-download-app btn-darken'></a>
          </div>
          <div id='mobile-settings-front'>
            <div class='btn-settings menu-option btn-darken btn-start-option'></div>
          </div>
        </div>
        <div id="start-bottom-middle">
          <a href='changelog.html' target="_blank" class="footer-after">ver 0.8.0</a>
          <a href='proxy.txt' target="_blank" data-l10n='index-proxy-sites'>proxy sites</a>
        </div>
        <div id='start-bottom-right-wrapper'>
          <div id='start-bottom-right'>
            <div class="language-select-wrap">
              <select class='language-select'></select>
            </div>
            <div class='btn-settings menu-option btn-darken btn-start-option'></div>
            <div class='btn-keybind menu-option btn-darken btn-start-option'></div>
            <div id='btn-start-fullscreen' class='btn-fullscreen-toggle menu-option btn-darken btn-start-option'></div>
            <div class='btn-start-mute btn-sound-toggle menu-option btn-darken btn-start-option audio-on-icon'></div>
          </div>
          <div id='mobile-download-app'>
            <a href='https://play.google.com/store/apps/details?id=io.surviv.surviv_io_mobile' target='_blank' class='btn-download-android btn-download-app-mobile btn-darken'></a>
            <a href='https://itunes.apple.com/us/app/surviv-io/id1401727934?ls=1&mt=8' target='_blank' class='btn-download-ios btn-download-app-mobile btn-darken'></a>
          </div>
        </div>
      </div>
      <!-- Modals -->
      <div id='ui-modal-keybind' class='ui-modal-keybind modal' oncontextmenu='return false;'>
        <div class='ui-modal-keybind-content modal-content modal-close'>
          <div id='ui-modal-keybind-header' class='modal-header'>
            <span id='ui-close-keybind' class='close close-corner'></span>
            <h2 data-l10n='index-customize-keybinds'>Customize Keybinds</h2>
          </div>
          <div id='ui-modal-keybind-body' class='modal-body'>
            <div id='ui-modal-keybind-list' class='js-keybind-list'></div>
            <div id='ui-modal-keybind-share'>
              <div class='ui-modal-keybind-share-row'>
                <div class='ui-modal-keybind-share-elem'>
                  <span data-l10n='index-keybind-link'>Share your keybinds with this code</span>:
                </div>
                <div class='ui-modal-keybind-share-elem'>
                  <div id='keybind-link-text'>
                    <div id='keybind-link'>aFvc42SfhpoFlrJKVkA1fx+5afasdf9034hfSF09nASqqF</div>
                    <span id='keybind-copy' class='copy-item btn-darken'></span>
                  </div>
                </div>
              </div>
              <span class='keybind-share-paste-text' data-l10n='index-keybind-paste'>Load keybinds using a code here</span><span>:</span>
              <div id='keybind-warning' class='link-warning'>Invalid code!</div>
              <div class='ui-modal-keybind-share-row'>
                <input type='text' class='menu-option' contenteditable="false" tabindex='0' autofocus placeholder='Paste a keybind code here' id='keybind-code-input' />
                <a class='btn-game-menu btn-darken' id='btn-keybind-code-load' data-l10n='index-keybind-apply'>Load</a>
              </div>
            </div>
          </div>
          <div id='ui-modal-keybind-footer' class='modal-footer modal-footer-round'>
            <a class='js-btn-keybind-share btn-game-menu btn-darken' data-l10n='game-share'>Share</a>
            <a class='js-btn-keybind-restore btn-game-menu btn-darken' data-l10n='game-restore-defaults'>Restore Defaults</a>
          </div>
        </div>
      </div>
      <!-- Loadouts -->
      <div id='modal-customize' class='modal'>
        <div class='ad-block-loadouts-left hide-on-mobile' id='surviv-io_300x600'></div>
        <div id='modal-customize-wrapper' class='modal-close'>
          <div id='modal-content-left' class='modal-content-shadow'>
            <div id='modal-customize-cat-title'></div>
            <div id="modal-customize-sort-wrap">
              <select id='modal-customize-sort'>
                <option id='customize-sort-newest' value='newest' data-l10n='loadout-newest'>Newest</option>
                <option id='customize-sort-alpha' value='alpha' data-l10n='loadout-alpha'>Alpha</option>
                <option id='customize-sort-rarity' value='rarity' data-l10n='loadout-rarity'>Rarity</option>
                <option id='customize-sort-subcat' value='subcat' data-l10n='loadout-subcat'>Category</option>
              </select>
            </div>
            <div id='modal-customize-close'>
              <span class='close close-corner'></span>
            </div>
            <div id='modal-customize-header' class='modal-header'></div>
            <div class='modal-disabled'>
              <div class='modal-disabled-message'>The Edge browser does not support custom cursors.</div>
            </div>
            <div id='modal-customize-body' class='modal-body'>
              <div id='modal-customize-item-header'>
                <div id='modal-customize-item-name'></div>
                <div id='modal-customize-item-rarity'></div>
                <div id='modal-customize-loading-container'>
                  <div id='modal-customize-loading'></div>
                </div>
              </div>
              <div id='modal-customize-list'></div>
            </div>
            <div id='modal-customize-footer' class='modal-footer modal-footer-round'>
              <div id='modal-customize-item-source'></div>
              <div id='modal-customize-item-lore'></div>
            </div>
          </div>
          <div id='modal-content-right-crosshair' class='modal-content-right modal-content-shadow'>
            <div class='modal-spacer'></div>
            <div class='modal-disabled'></div>
            <div id='customize-crosshair-parent'>
              <div id='customize-crosshair-selected'>
                <div class="customize-item-image customize-crosshair-image" draggable="false"></div>
              </div>
              <div id='customize-crosshair-sliders'>
                <div class="crosshair-hex-outer">
                  <span>#</span><input type="text" id='color-picker-hex'>
                </div>
                <section id="color-picker"></section>
                <div class="crosshair-slider-container">
                  <p class='' data-l10n='loadout-size'>Size</p>
                  <input type="range" min="0.25" max="1.0" value="0.5" step='0.025' class="crosshair-slider" id="crosshair-size">
                </div>
                <div class="crosshair-slider-container">
                  <p class='' data-l10n='loadout-stroke'>Stroke</p>
                  <input type="range" min="0.0" max="1.5" value="0.0" step='0.025' class="crosshair-slider" id="crosshair-stroke">
                </div>
              </div>
            </div>
          </div>
          <div id='modal-content-right-emote' class='modal-content-right modal-content-shadow'>
            <div id='customize-emote-parent'>
              <div id='customize-emote-wheel' class='ui-emote-wheel'>
                <div id='customize-emote-middle' class='ui-emote-middle ui-emote-circle ui-emote-parent'>
                  <div class='ui-emote ui-emote-bg-circle'></div>
                  <div class='ui-emote ui-emote-hl'></div>
                  <div class='customize-emote-slot customize-item-image ui-emote-image'></div>
                </div>
                <div id='customize-emote-top' class='ui-emote-top ui-emote-quarter ui-emote-parent' data-slot='emoteTop' data-idx='0'>
                  <div class='ui-emote ui-emote-bg-quarter'></div>
                  <div class='ui-emote ui-emote-hl'></div>
                  <div class='customize-emote-slot customize-item-image ui-emote-image'></div>
                  <div class='customize-col customize-col-small' draggable="true"></div>
                </div>
                <div id='customize-emote-right' class='ui-emote-right ui-emote-quarter ui-emote-parent' data-slot='emoteRight' data-idx='1'>
                  <div class='ui-emote ui-emote-bg-quarter'></div>
                  <div class='ui-emote ui-emote-hl'></div>
                  <div class='customize-emote-slot customize-item-image ui-emote-image'></div>
                  <div class='customize-col customize-col-small' draggable="true"></div>
                </div>
                <div id='customize-emote-bottom' class='ui-emote-bottom ui-emote-quarter ui-emote-parent' data-slot='emoteBottom' data-idx='2'>
                  <div class='ui-emote ui-emote-bg-quarter'></div>
                  <div class='ui-emote ui-emote-hl'></div>
                  <div class='customize-emote-slot customize-item-image ui-emote-image'></div>
                  <div class='customize-col customize-col-small' draggable="true"></div>
                </div>
                <div id='customize-emote-left' class='ui-emote-left ui-emote-quarter ui-emote-parent' data-slot='emoteLeft' data-idx='3'>
                  <div class='ui-emote ui-emote-bg-quarter'></div>
                  <div class='ui-emote ui-emote-hl'></div>
                  <div class='customize-emote-slot customize-item-image ui-emote-image'></div>
                  <div class='customize-col customize-col-small' draggable="true"></div>
                </div>
              </div>
              <div id='customize-emote-autos'>
                <div id='customize-emote-win' class='ui-emote-middle ui-emote-circle ui-emote-parent' data-slot='emoteWin' data-idx='4'>
                  <div class='ui-emote ui-emote-auto-trash'></div>
                  <div class='ui-emote ui-emote-auto-icon ui-emote-auto-chicken'></div>
                  <div class='ui-emote ui-emote-bg-circle-outer'></div>
                  <div class='ui-emote ui-emote-bg-circle'></div>
                  <div class='ui-emote ui-emote-hl'></div>
                  <div class='customize-emote-slot customize-item-image'></div>
                  <div class='customize-col customize-col-large' draggable="true"></div>
                </div>
                <div id='customize-emote-death' class='ui-emote-middle ui-emote-circle ui-emote-parent' data-slot='emoteDeath' data-idx='5'>
                  <div class='ui-emote ui-emote-auto-trash'></div>
                  <div class='ui-emote ui-emote-auto-icon ui-emote-auto-skull'></div>
                  <div class='ui-emote ui-emote-bg-circle-outer'></div>
                  <div class='ui-emote ui-emote-bg-circle'></div>
                  <div class='ui-emote ui-emote-hl'></div>
                  <div class='customize-emote-slot customize-item-image'></div>
                  <div class='customize-col customize-col-large' draggable="true"></div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div id='modal-settings' class='modal'>
        <div class='modal-content modal-close'>
          <div class='modal-header'>
            <span class='close close-corner'></span>
            <h2 data-l10n='index-settings'>Settings</h2>
          </div>
          <div id='modal-settings-body' class='modal-body'>
            <div id='language-select-mobile-wrapper' class='modal-settings-item'>
              <div class="language-select-wrap">
                <select class='language-select'></select>
              </div>
            </div>
            <div id='modal-settings-high-res' class='modal-settings-item'>
              <input id='highResTex' type='checkbox'><p class='modal-settings-checkbox-text' data-l10n='index-high-resolution'>High resolution (check to increase visual quality)</p>
            </div>
            <div class='modal-settings-item hide-on-mobile'>
              <input id='screenShake' type='checkbox'><p class='modal-settings-checkbox-text' data-l10n='index-screen-shake'>Screen shake</p>
            </div>
            <div class='modal-settings-item'>
              <input id='anonPlayerNames' type='checkbox'><p class='modal-settings-checkbox-text' data-l10n='index-anon-player-names'>Anonymize player names</p>
            </div>
            <div class="modal-settings-item slider-container main-volume-slider">
              <p class='modal-slider-text' data-l10n='index-master-volume'>Master Volume</p>
              <input type="range" min="0" max="100" value="50" class="slider sl-master-volume" id="">
            </div>
            <div class="modal-settings-item slider-container main-volume-slider">
              <p class='modal-slider-text' data-l10n='index-sfx-volume'>SFX Volume</p>
              <input type="range" min="0" max="100" value="50" class="slider sl-sound-volume" id="">
            </div>
            <div class="modal-settings-item slider-container main-volume-slider">
              <p class='modal-slider-text' data-l10n='index-music-volume'>Music Volume</p>
              <input type="range" min="0" max="100" value="50" class="slider sl-music-volume" id="">
            </div>
            <div id='settings-links'>
              <a href='#' class="btn-cookie-settings footer-after">cookie settings</a>
              <a href='privacy.html' target="_blank" class="footer-after" data-l10n='index-privacy'>privacy</a>
              <a href='attribution.txt' target="_blank" class="footer-after" data-l10n='index-attributions'>attributions</a>
              <a href='hof.html' target="_blank" data-l10n='index-hof'>HOF</a>
            </div>
          </div>
          <div class='modal-footer'></div>
        </div>
      </div>
      <div id='modal-hamburger' class='modal'>
        <div class='modal-content modal-close'>
          <div class='modal-header'>
            <span class='close close-hamburger icon-hamburger'></span>
            <h2>&nbsp</h2>
          </div>
          <div id='modal-hamburger-body' class='modal-body'>
            <div id='modal-hamburger-leaderboards'>
              <a href='/stats' target='_blank' class='btn-leaderboard-stats-link menu-option btn-darken' data-l10n='index-leaderboards'>Leaderboards</a>
            </div>
            <div class='modal-divider'></div>
            <div class='btn-social-wrapper'>
              <a href='https://facebook.com/surviviogame' target='_blank' class='btn-social btn-darken btn-facebook'></a>
              <a href='https://twitter.com/survivio' target='_blank' class='btn-social btn-darken btn-twitter'></a>
              <a href='https://www.instagram.com/surviviogame/' target='_blank' class='btn-social btn-darken btn-instagram'></a>
              <a href='https://discord.gg/survivio' target='_blank' class='btn-social btn-darken btn-discord'></a>
              <!-- <a href='https://www.youtube.com/c/survivio?sub_confirmation=1' target='_blank' class='btn-social btn-darken btn-youtube'></a> -->
            </div>
            <div class='modal-divider'></div>
            <div id='modal-hamburger-bottom'>
              <a href='changelog.html' class="footer-after">ver 0.8.0</a>
              <a href='#' class="btn-cookie-settings footer-after">cookie settings</a>
              <a href='privacy.txt' target="_blank" class="footer-after">privacy</a>
              <a href='attribution.txt' target="_blank">attributions</a>
            </div>
          </div>
        </div>
      </div>
      <div id='modal-notification' class='modal'>
        <div class='modal-content modal-close'>
          <div class='modal-header'>
            <span class='close close-corner'></span>
            <h2>Alert</h2>
          </div>
          <div class='modal-body'>
            <p class='modal-body-text'></p>
          </div>
          <div class='modal-footer modal-footer-round'>
            <h3 class='close close-footer'>OK</h3>
          </div>
        </div>
      </div>
      <div id='modal-news' class='modal'>
        <div class='modal-content modal-close'>
          <div class='modal-header'>
            <span class='close close-corner'></span>
            <h2>New Update!</h2>
          </div>
          <div class='modal-body'>
            <div class='modal-body-header'>Loadouts</div>
            <div class='modal-body-image'></div>
          </div>
          <div class='modal-footer modal-footer-round'>
            <h3 class='close close-footer'>OK</h3>
          </div>
        </div>
      </div>
      <div id='modal-refresh' class='modal'>
        <div class='modal-content modal-close'>
          <div class='modal-header'>
            <span class='close close-corner'></span>
            <h2>New Update</h2>
          </div>
          <div class='modal-body'>
            <p class='modal-body-text'>A new version of surviv.io is available!<br><br>Press "OK" below to reload the page.</p>
          </div>
          <div class='modal-footer modal-footer-round'>
            <h3 id='force-refresh' class='close close-footer'>OK</h3>
          </div>
        </div>
      </div>
      <div id='modal-create-account' class='modal modal-account'>
        <div class='modal-content modal-close'>
          <div class='modal-header modal-header-name'>
            <span class='close-loadouts close close-corner'></span>
            <h2 id='modal-account-name-title' data-l10n='index-log-in-desc'>Log In / Create Account</h2>
          </div>
          <div class='modal-body modal-body-name'>
            <p class='modal-body-text' data-l10n='index-create-account-prompt-1'>Log in to access this feature!</p>
            <div class='login-options-content'></div>
          </div>
          <div class='modal-footer modal-footer-name modal-footer-round'>
            <h3 class='close close-footer' data-l10n='index-cancel'>Cancel</h3>
          </div>
        </div>
      </div>
      <div id='modal-screen-block'>
        <div id='modal-item-confirm' class='modal'>
          <div class='modal-content modal-close'>
            <div class='modal-header modal-header-name'>
              <h2 id='modal-account-name-title'>You got a new item!</h2>
            </div>
            <div class='modal-body modal-body-name'>
              <div id='modal-item-confirm-image-outer'>
                <div id='modal-item-confirm-image-inner'></div>
              </div>
              <div class='modal-settings-item'>
                <p id='modal-item-confirm-name' class='modal-body-text'>Karambit Prismatic</p>
              </div>
            </div>
            <div class='modal-footer modal-footer-name modal-footer-round'>
              <h3 class='close close-footer' data-l10n='index-confirm'>Confirm</h3>
            </div>
          </div>
        </div>
      </div>
      <div id='modal-cookie-settings' class='modal'>
        <div class='modal-content modal-close'>
          <div class='modal-header'>
            <span class='close close-corner'></span>
            <h2>Cookie Settings</h2>
          </div>
          <div class='modal-body'>
            <p class='modal-body-text'>We use cookies to personalize content and ads, to provide social media features, and to analyze our traffic. We also share information about your use of our site with our social media, advertising and analytics partners who may combine it with other information that you've provided to them or that they've collected from your use of their services. You consent to our cookies if you continue to use our website. Click <a href='#' id='btn-cookie-opt-out' class='close'>here</a> to opt out of using cookies.</p>
          </div>
          <div class='modal-footer modal-footer-round'>
            <h3 class='close close-footer'><div class='btn-cookies-close btn-darken'>Got it!</div></h3>
          </div>
        </div>
      </div>
    </div>
  <script type="text/javascript" src="js/manifest.53537e9a.js"></script><script type="text/javascript" src="js/vendor.a14ce1ae.js"></script><script type="text/javascript" src="js/app.e1d9e34d.js"></script></body>
</html>
