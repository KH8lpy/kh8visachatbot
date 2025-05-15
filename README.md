<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>Chatbot Widget</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <style>
      html, body {
        height: 100%;
        margin: 0;
        padding: 0;
        background-color: transparent;
        overflow: hidden;
      }
    </style>
  </head>
  <body>
    <script>
      (function(){
        if (!window.chatbase || window.chatbase("getState") !== "initialized") {
          window.chatbase = (...args) => {
            if (!window.chatbase.q) window.chatbase.q = [];
            window.chatbase.q.push(args);
          };
          window.chatbase = new Proxy(window.chatbase, {
            get(target, prop) {
              if (prop === "q") return target.q;
              return (...args) => target(prop, ...args);
            }
          });
        }
        const onLoad = function() {
          const script = document.createElement("script");
          script.src = "https://www.chatbase.co/embed.min.js";
          script.id = "emu8MBJak602pkUTLE-bD"; // your bot ID
          script.domain = "www.chatbase.co";
          document.body.appendChild(script);
        };
        if (document.readyState === "complete") {
          onLoad();
        } else {
          window.addEventListener("load", onLoad);
        }
      })();
    </script>
  </body>
</html>
