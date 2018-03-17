.. title: Mongoose + Heroku + mLab
.. slug: mongoose-+-heroku-+-mlab
.. date: 2017-06-28 00:57:17 UTC+02:00
.. tags: mongoose, heroku, mlab
.. author: Alhern
.. link:
.. description:
.. category:


1. Configurate Heroku with::

    heroku config:set MONGOLAB_URI=mongodb://[username]:[password]@xx000000.mlab.com:00000/[project-name]


2. Add to app.js::

    const mongodbUri = process.env.MONGOLAB_URI;

    mongoose.connect(mongodbUri, (err, res) => {
        if (err) {
            console.log(err);
        } else {
            console.log('success!!!!!!!!!');
        }
    });


3. At the bottom::

    const port = process.env.PORT

    app.listen(process.env.PORT);

