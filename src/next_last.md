# next, last
- 今回は使用頻度の高い `next`, `last` に関して紹介します

## next
    my @languages = qw/c ruby papix perl python java c++/;
    for my $lang (@languages) {
        if ($lang eq "perl") {
            print "Find Perl\n";
            next;
        }
        print "$lang\n";
    }

- 試しに上記のコードを実行してみましょう

## 実行結果 (next)
    c
    ruby
    papix
    Find Perl
    python
    java
    c++

- "Find Perl" という文字列は出力されますが, `perl` という文字列は出力されません
    - これは `next` に到達すると, 残りの処理を行わず, 次のループ `($lang[4])` を開始するためです

## last
    my @languages = qw/c ruby papix perl python java c++/;
    for my $lang (@languages) {
        if ($lang eq "perl") {
            print "Find Perl\n";
            last;
        }
        print "$lang\n";
    }

- 試しに上記のコードを実行してみましょう
    - `next` を `last` に書き換えるのみです

## 実行結果 (last)
    c
    ruby
    papix
    Find Perl

- `$lang[3]` の `perl` という文字列が一致して `if` 文内の `last` に到達した時点で `for` ループを抜けます. そのため `python`, `java`, `c++` という文字列が表示されません