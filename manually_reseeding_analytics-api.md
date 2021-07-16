# Manually Reseeding for Analytics-API

Set up a fresh db, seed it and then run the analytics seed. Next run rails runner seed from analytics-api/spec/dummy/db to create pci layouts. Then run seed_questions and create_for_facility scripts from (registries-implementation)[reg-imp] to create questionnaires for v4.4. You'll also want to seed v5.0 by running seed_version_questions and create_version_for scripts. And then finally run the update_edge_targets script from the registries-implementation. If you need additional responses 

- [ ] rails db:drop
- [ ] rails db:create
- [ ] rails db:migrate
- [ ] rails db:seed
- [ ] rails runner “require Analytics::Api::Engine.root.join(‘spec/dummy/db/seeds.rb’).to_s”
- [ ] bundle exec rake ncdr:cath_pci:seed_questions
- [ ] bundle exec rake ncdr:cath_pci:create_for_facility[1]
- [ ] bundle exec rake ncdr:cath_pci:seed_version_questions['5.0']
- [ ] bundle exec rake ncdr:cath_pci:create_version_for_facility[1,'5.0']
- [ ] bundle exec rake registries:update_edge_targets

[reg-imp]: https://github.com/q-centrix/registries-implementations#questionnaire-creation-on-qweb
