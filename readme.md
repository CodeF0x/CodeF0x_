0cf788dfee0447b69d316483e8615eb9
Error: ENOENT: no such file or directory, open 'spotify-auth.json'
    at Object.openSync (fs.js:465:3)
    at Object.readFileSync (fs.js:368:35)
    at getSpotifyToken (/home/runner/work/spotify-stats/spotify-stats/index.js:34:24)
    at getSpotifyData (/home/runner/work/spotify-stats/spotify-stats/index.js:86:23)
    at main (/home/runner/work/spotify-stats/spotify-stats/index.js:16:29)
    at /home/runner/work/spotify-stats/spotify-stats/index.js:171:9
    at Object.<anonymous> (/home/runner/work/spotify-stats/spotify-stats/index.js:172:3)
    at Module._compile (internal/modules/cjs/loader.js:1256:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:1277:10)
    at Module.load (internal/modules/cjs/loader.js:1105:32) {
  errno: -2,
  syscall: 'open',
  code: 'ENOENT',
  path: 'spotify-auth.json'
}
