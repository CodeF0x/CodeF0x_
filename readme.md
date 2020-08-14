Error: ENOENT: no such file or directory, open 'spotify-auth.json'
    at Object.openSync (fs.js:465:3)
    at Object.readFileSync (fs.js:368:35)
    at getSpotifyToken (/home/runner/work/spotify-stats/spotify-stats/index.js:32:24)
    at getSpotifyData (/home/runner/work/spotify-stats/spotify-stats/index.js:84:23)
    at main (/home/runner/work/spotify-stats/spotify-stats/index.js:14:29)
    at /home/runner/work/spotify-stats/spotify-stats/index.js:169:9
    at Object.<anonymous> (/home/runner/work/spotify-stats/spotify-stats/index.js:170:3)
    at Module._compile (internal/modules/cjs/loader.js:1256:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:1277:10)
    at Module.load (internal/modules/cjs/loader.js:1105:32) {
  errno: -2,
  syscall: 'open',
  code: 'ENOENT',
  path: 'spotify-auth.json'
}
