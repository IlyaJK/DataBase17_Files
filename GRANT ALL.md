--SET ROLE user_rusnak;
--RESET ROLE;
--SELECT * FROM post;

--GRANT USAGE ON schema forum TO admin_rusnak, moderator_rusnak, user_rusnak, anonim_rusnak

--GRANT ALL ON forum.post TO admin_rusnak, moderator_rusnak;
--GRANT ALL ON forum.account TO admin_rusnak;
--GRANT ALL ON forum.tag TO admin_rusnak;
--GRANT ALL ON forum.person TO admin_rusnak;
--GRANT ALL ON forum.tag_name TO admin_rusnak;
--GRANT ALL ON forum.likes TO admin_rusnak, moderator_rusnak, user_rusnak;

--GRANT SELECT, UPDATE, DELETE ON forum.post, forum.tag, forum.likes,
                         forum.tag_name, forum.person TO user_rusnak;
--GRANT SELECT ON forum.account, forum.person TO user_rusnak

--GRANT ALL ON forum.account, forum.post, forum.likes, forum.person,
                          forum.tag, forum.tag_name TO admin_rusnak;
--GRANT ALL ON forum.account, forum.post, forum.likes, forum.person,
                          forum.tag, forum.tag_name TO admin_rusnak;

--GRANT SELECT ON forum.account TO moderator_rusnak;
--GRANT SELECT, UPDATE ON forum.account TO admin_rusnak;

--ALTER TABLE forum.post ENABLE ROW LEVEL SECURITY;
--ALTER TABLE forum.person ENABLE ROW LEVEL SECURITY;
--ALTER TABLE forum.likes ENABLE ROW LEVEL SECURITY;

--CREATE POLICY read_post ON forum.post FOR SELECT TO admin_rusnak, moderator_rusnak,
                                                          user_rusnak, anonim_rusnak
--USING (true)

--CREATE POLICY read_post ON forum.post FOR UPDATE TO user_rusnak
--USING (current_setting ('user_id')::int = person_id);

--CREATE POLICY read_post ON forum.post FOR DELETE TO user_rusnak
--USING (true);
