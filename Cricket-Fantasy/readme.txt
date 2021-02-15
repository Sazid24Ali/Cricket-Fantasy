UI files 
*////////////////////////----------------//////////////////////////////*
inside UI folder 
note : - some proerties in popUpBox,ui missing as i have manually added them

basic shortcuts 
*////////////////////////----------------//////////////////////////////


basic shortcuts 
*////////////////////////----------------//////////////////////////////*
close window --- ESC key

In main window:
ctrl+O -- open team window
ctrl+Q -- quit
ctrl+N -- new team window
ctrl+S -- to save to database

For eroror information pop up
to exit -- click on the icon or press ok


Database setup the database was created in Sqlite3 studio 
*/////////////////////////-------------------------///////////////////////////////*
CREATE TABLE [match] (
    Player   TEXT NOT NULL ON CONFLICT ROLLBACK
                          UNIQUE
                          PRIMARY KEY ON CONFLICT ROLLBACK,
    Scored   INTEGER      NOT NULL ON CONFLICT ROLLBACK,
    Faced    INTEGER      NOT NULL ON CONFLICT ROLLBACK,
    Fours    INTEGER      NOT NULL ON CONFLICT ROLLBACK,
    Sixes    INTEGER      NOT NULL ON CONFLICT ROLLBACK,
    Bowled   INTEGER      NOT NULL ON CONFLICT ROLLBACK,
    Maiden   INTEGER      NOT NULL ON CONFLICT ROLLBACK,
    Given    INTEGER      NOT NULL ON CONFLICT ROLLBACK,
    Wkts                  NOT NULL ON CONFLICT ROLLBACK,
    Catches  INTEGER      NOT NULL ON CONFLICT ROLLBACK,
    Stumping INTEGER      NOT NULL ON CONFLICT ROLLBACK,
    RO       INTEGER      NOT NULL ON CONFLICT ROLLBACK
);

CREATE TABLE teams (
    name    TEXT NOT NULL ON CONFLICT ROLLBACK,
    players BLOB          NOT NULL,
    value   BLOB          NOT NULL ON CONFLICT ROLLBACK
);

CREATE TABLE stats (
    player  TEXT    REFERENCES [match] (Player) 
                    NOT NULL ON CONFLICT ROLLBACK,
    matches INTEGER NOT NULL ON CONFLICT ROLLBACK,
    runs    INTEGER NOT NULL ON CONFLICT ROLLBACK,
    [100s]  INTEGER NOT NULL ON CONFLICT ROLLBACK,
    [50s]   INTEGER NOT NULL ON CONFLICT ROLLBACK,
    value   INTEGER NOT NULL ON CONFLICT ROLLBACK,
    ctg     TEXT    NOT NULL ON CONFLICT ROLLBACK
);
