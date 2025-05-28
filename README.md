# my-project
##概念
このプロジェクトはWordPressについて復習するために作成しました
##目的
1.	テンプレートタグ記述場所の把握
2.	タグの概要把握
##トップページ
<div style="background-color: #d0f0c0; padding: 10px;">
1.header.php
テンプレートタグ	説明
php wp_nav_menu();	登録済みのナビゲーションメニューを出力
php get_template_part('template-parts/header');	別のテンプレートファイルを読み込み
php get_header(); 	ヘッダーをロード
php get_custom_header(); 	カスタムヘッダー情報を取得
php header_image(); 	カスタムヘッダー画像のURLを取得
php has_custom_header();	カスタムヘッダーが設定されているか確認
php wp_title();	ページタイトルを表示
php get_home_url(); 	ホームURLを取得
php language_attributes();	HTMLタグの lang 属性を追加
この他にもheader.php に組み込めるテンプレートタグはありますが、どのような情報を表示し
</div>
<div style="background-color: #add8e6; padding: 10px;">
  2.index.php
テンプレートタグ	説明
基本情報
php get_header();	ヘッダーを読み込む
php get_footer();	フッターを読み込む
php get_sidebar(); 	サイドバーを読み込む
php bloginfo('name');	サイト名を表示
php bloginfo('description');	サイトのキャッチフレーズを表示
記事ループ（投稿一覧）
php if ( have_posts() ) : while ( have_posts() ) : the_post(); 	投稿ループの開始
php the_title(); 	投稿タイトルを表示
php the_content(); 	投稿内容を表示
php the_excerpt();	投稿の抜粋を表示
php the_permalink(); 投稿のリンクを取得
php the_post_thumbnail(); アイキャッチ画像を表示
php the_category(); 投稿のカテゴリーを表示
php the_tags(); 投稿のタグを表示
php endwhile; endif; ループの終了
投稿・コンテンツ関連
php the_ID();	投稿のIDを取得
php the_author(); 投稿の作者を表示
php the_date(); 	投稿の日付を表示
php edit_post_link(); 編集リンクを表示
php get_post_meta($post->ID, 'custom_field', true); 	カスタムフィールドの値を取得
カスタム投稿・クエリ
php query_posts($args); 	メインクエリを変更
php $query = new WP_Query($args);	カスタムクエリを作成
php get_post_type(); 	投稿タイプを取得
php post_type_archive_title(); 	カスタム投稿タイプのアーカイブタイトルを取得
ナビゲーション
php wp_nav_menu(); 	カスタムメニューを表示
php previous_posts_link();	前の投稿ページへのリンク
php next_posts_link();	次の投稿ページへのリンク
動的コンテンツ
php get_template_part('template-parts/content'); 	分割されたテンプレートを読み込む
php comments_template(); コメントフォームを表示
php get_search_form(); 	検索フォームを表示
メディア関連
php wp_get_attachment_url($attachment_id); 	添付ファイルのURLを取得
php get_the_post_thumbnail_url(); 	投稿のアイキャッチ画像URLを取得
php get_header_image(); 	カスタムヘッダー画像URLを取得
ユーザー・ログイン関連
php wp_login_url(); 	ログインページのURLを取得
php wp_logout_url(); 	ログアウトURLを取得
php wp_register_url(); 	ユーザー登録URLを取得
php current_user_can('edit_posts'); 	ユーザーの権限をチェック
その他便利なタグ
php is_home(); 	現在のページがホームか判定
php is_front_page(); 	フロントページかどうかを判定
php is_single(); 	シングル投稿ページか判定
php is_page();	固定ページか判定
php is_category(); 	カテゴリページか判定
  </div>
  <div style="background-color: #ffcc99; padding: 10px;">
3.footer.php
テンプレートタグ	説明	使用例
wp_footer()	プラグインやテーマのスクリプトを適切に読み込む
get_template_part()	フッターの一部を別ファイルから読み込む	
bloginfo('name')	サイト名を表示
bloginfo('description')	サイトの説明を表示	
echo　home_url()	ホームページの URL を取得	
wp_nav_menu(array('theme_location' => 'footer-menu'))	フッターメニューを表示	
&copy; php echo date('Y'); date('Y')	現在の年を取得	
is_active_sidebar('footer-1')	ウィジェットエリアが有効か判定
register_sidebar()	フッター用のウィジェットエリアを登録	register_sidebar(array(...));
register_nav_menu()	フッターナビゲーションを登録	register_nav_menu('footer-menu', 'Footer Menu');
</div>
