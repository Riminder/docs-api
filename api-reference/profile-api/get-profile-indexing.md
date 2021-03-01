---
description: This endpoint allows to retrieve  the Profile object.
---

# GET: /profile/indexing

One of key , reference or email parameters should be provided to identify the profile.

{% api-method method="get" host="https://api.hrflow.ai" path="/v1/profile/indexing" %}
{% api-method-summary %}
/profile/indexing
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="X-API-KEY" type="string" required=true %}
Authentication token.
{% endapi-method-parameter %}

{% api-method-parameter name="X-USER-EMAIL" type="string" required=true %}
User's email
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="source\_key" type="string" required=true %}
The source unique identifier
{% endapi-method-parameter %}

{% api-method-parameter name="key" type="string" required=false %}
The profile unique identifier
{% endapi-method-parameter %}

{% api-method-parameter name="reference" type="string" required=false %}
The profile's reference
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=false %}
The profile's email
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Profile object is successfully retrieved
{% endapi-method-response-example-description %}

```bash
{
    "code": 200,
    "message": "Profile details",
    "data": {
        "id": id,
        "key": "profile_key",
        "reference": null,
        "archive": null,
        "consent_algorithmic": {
            "owner": {
                "parsing": true,
                "revealing": false,
                "embedding": true,
                "searching": false,
                "scoring": true,
                "reasoning": false
            },
            "controller": {
                "parsing": true,
                "revealing": false,
                "embedding": true,
                "searching": false,
                "scoring": true,
                "reasoning": false
            }
        },
        "source": {
            "id": id,
            "key": "source_key",
            "name": "Source name",
            "type": "dropzone",
            "subtype": "dropzone"
        },
        "updated_at": "2020-07-24T14:17:34+0000",
        "created_at": "2020-04-23T08:18:54+0000",
        "info": {
            "full_name": "Harry Potter",
            "first_name": "Harry",
            "last_name": "Potter",
            "email": "harry.potter@hrflow.ai",
            "phone": null,
            "location": {
                "text": null,
                "lat": null,
                "lng": null,
                "gmaps": null,
                "fields": []
            },
            "urls": {
                "from_resume": [],
                "linkedin": "",
                "twitter": "",
                "facebook": "",
                "github": ""
            },
            "picture": null,
            "gender": "F",
            "summary": "Product Manager / Product Owner\nDiplômée en Système information et Génie logiciel en acquérant plus de 7 ans d ' expériences en Analyste d ' affaires dont 2 ans en Product Owner .\nLa flexibilité reste l ' un de mes plus grands atouts . Animé par la mise en æuvre de stratégies marketing produit visant à mettre en place les outils pour\nfaire interagir l ' entreprise . Leader naturel faisant preuve de diplomatie et d ' écoute . Egalement force de proposition et créative , souhaitant contribuer à\nla planification stratégique des systèmes d ' information . Capable de servir d ' intermédiaire entre le Client et l ' équipe IT en vue de mon parcours\ntechnique et fonctionnel . Mon esprit de synthèse et d ' analyse son mes forces . Souhaitant intégrer vos équipes et relever de nouveau défis , pour aller\nplus loin .\nRésumé de mes qualifications\nComprendre le contexte d ' affaires et l ' impact des projets sur les processus de l ' organisation\nContribuer à la planification stratégique des systèmes d ' information\nDocumenter la portée des projets , leurs objectifs , leur valeur ajoutée ou encore les bénéfices attendus\nTraduire les exigences commerciales en objectifs techniques pour les équipes de développement\nAppliquer des outils poussés de modélisation et d ' analyse\nAssurer un suivi pendant la mise en cuvre\nContribuer à la gestion du backlog\nMéthodologies Agile : Scrum et Kanban , formation PSPO en cheminement"
        },
        "text_language": "fr",
        "text": "product manager / product owner\ndiplômée en système information et génie logiciel en acquérant plus de 7 ans d ' expériences en analyste d ' affaires dont 2 ans en product owner .\nla flexibilité reste l ' un de mes plus grands atouts . animé par la mise en æuvre de stratégies marketing produit visant à mettre en place les outils pour\nfaire interagir l ' entreprise . leader naturel faisant preuve de diplomatie et d ' écoute . egalement force de proposition et créative , souhaitant contribuer à\nla planification stratégique des systèmes d ' information . capable de servir d ' intermédiaire entre le client et l ' équipe it en vue de mon parcours\ntechnique et fonctionnel . mon esprit de synthèse et d ' analyse son mes forces . souhaitant intégrer vos équipes et relever de nouveau défis , pour aller\nplus loin .\nrésumé de mes qualifications\ncomprendre le contexte d ' affaires et l ' impact des projets sur les processus de l ' organisation\ncontribuer à la planification stratégique des systèmes d ' information\ndocumenter la portée des projets , leurs objectifs , leur valeur ajoutée ou encore les bénéfices attendus\ntraduire les exigences commerciales en objectifs techniques pour les équipes de développement\nappliquer des outils poussés de modélisation et d ' analyse\nassurer un suivi pendant la mise en cuvre\ncontribuer à la gestion du backlog\nméthodologies agile : scrum et kanban , formation pspo en cheminement\nexpériences professionnelles\nbanque nationale canada - montréal\naout 2017 à aujourd ' hui\nposte : analyste d ' affaires livraison des solutions web transactionnels / product owners ( web et mobile )\nrefonte du site internet sbipvl vers sbipv2 / livraison du projet authentification et identification faciale et identitaire d ' un prospect\nsoutenir les utilisateurs dans la résolution des problèmes ti , accompagner les différentes directions dans la définition\nde leurs besoins en matière de technologie et de processus\nassurer une relation d ' affaires agile et efficace avec des équipes clients en veillant à répondre à leurs besoins ,\net en agissant comme agent de liaison entre les différentes parties prenantes .\nrédiger le roadmap , le présenter aux équipes et le maintenir à jour\ngérer le backlog : ecriture des epics , rédaction des user stories , écriture des critères d ' acceptations\nsuivre les kpi ' s , identifier à l ' aide des dtm pour le front - end , datahub pour identifier les métriques back - end\naider à effectuer les tests d ' acceptations des utilisateurs , coordonner les différents essais\nsolidifier les exigences fonctionnelles\nrédaction du rfp ( request of proposal , processus d ' appel d ' offres )\nmanager l ' orchestration des api ' s avec l ' orchestrateur camunda\ndévelopper et mettre en æuvre des solutions , des positionnements et des stratégies en appui aux équipes impliquées en vue de réaliser les\nstratégies proposées , répondre aux besoins des membres , atteindre les objectifs d ' affaires visés , et maximiser la croissance\nagir à titre de responsable de la vigie sur les tendances du marché et de l ' offre de la concurrence\nreprésenter son unité d ' affaires auprès des divers partenaires et négocier , le cas échéant , les ententes et les partenariats pertinents\nenvironnements : jira , confluence , sharepoint , office , teams , soa , soapui , suivi des api ' s\nhydro québec ( mandat cgi ) - montréal\nmai 2017 à aout 2017\nposte : analyste d ' affaires et analyste fonctionnelles - moa\nplanisware : projet ops ( optimisation de processus du système )\nanalyser les besoins du client et l ' accompagner dans la définition de ses besoins , l ' orienter dans les solutions fonctionnelles appropriées en\ntenant compte des engagements budgétaires et des délais de livraison .\norienter les équipes de développement dans leurs analyses et résoudre les problèmes fonctionnels survenant en cours de projet afin que les\nsolutions proposées soient cohérentes et tiennent compte tant des besoins des utilisateurs et de l ' architecture de système que des\ncontraintes à respecter .\nproduction de différents livrables soit : analyse d ' impact , cas d ' utilisation , spécification fonctionnel , spécification détaillée , stratégie\nd ' essais , plan d ' essais , cas d ' essais et estimation des efforts .\ncoordonner les différents essais\nparticipation aux comités avec le client , revue des spécifications fonctionnelles\nenvironnement : planisware , word , hp alm , tfs\nville de montréal ( mandat cgi ) - montréal\nseptembre 2016 à mai 2017\nposte : analyste d ' affaires et analyste fonctionnelles - moa\nncpc ( nouveau code de procédure civil )\nanalyser les besoins du client et l ' accompagner dans la définition de ses besoins , l ' orienter dans les solutions fonctionnelles appropriées en\ntenant compte des engagements budgétaires et des délais de livraison .\norienter les équipes de développement dans leurs analyses et résoudre les problèmes fonctionnels survenant en cours de projet afin que les\nsolutions proposées soient cohérentes et tiennent compte tant des besoins des utilisateurs et de l ' architecture de système que des\ncontraintes à respecter .\nproduction de différents livrables soit : analyse d ' impact , cas d ' utilisation , spécification fonctionnel , spécification détaillée , stratégie\nd ' essais , plan d ' essais , cas d ' essais et estimation des efforts .\ncoordonner les différents essais\nparticipation aux comités avec le client , revue des spécifications fonctionnelles\nenvironnement : natural database , natural , emulateur mocha ibm , système stop +\ndesjardins fcdq ( mandat cgi ) - montréal\nfévrier 2016 à août 2016\nposte : analyste - moa\nprojet etfe ( transfert de fonds electronique ) : collaborer au développement des projets technologiques en matière de tests d ' assurance\nqualité , d ' implantation et d ' expérimentation . jouer un rôle clé pour les activités de contrôle de qualité dans le cadre de l ' initiative de\nmodernisation des applications de transferts électroniques ( dépôt retrait direct , système de perception de compte et edi ) .\ndéterminer , écrire et exécuter les scénarios de tests à réaliser selon le mandat d ' intégration\névaluer la charge de préparation et d ' exécution des tests pour son périmètre\ncommuniquer les exigences , documentation et outils à l ' intégrateur\nsupporter l ' intégrateur dans ses activités de développement\nexécuter des tests de certification\nenvironnement : normes acp , jira\nalten sir\nmai 2015 au 2 août 2015\npage 1 sur 2 poste : analyste d ' affaires en interne - moa\nencadrer la clientèle dans l ' expression de besoin de leurs besoin d ' affaires\nrédaction des besoins et les exigences d ' affaires dans des documents structurés et complet\nmandat cabinet aubay - octobre 2013 à janvier 2015\ncrédit agricole consumer finance ( mandat cabinet aubay ) novembre 2014 à janvier 2015\nposte : analyste d ' affaires - analyste fonctionnelle - moa\nprojet lld location de véhicule longue durée permettant de financer les flottes des véhicules des particuliers . lld mets à disposition mets à\ndisposition le véhicule et les prestations de service\nrecueillir des informations d ' affaires\nanalyser les processus et modéliser les besoins du client\nrédaction des besoins en spécifications technique dans des documents structurés et complet\nenvironnement technique : cobol , db2\nbnp paribas ( mandat cabinet aubay )\naout 2014 à octobre 2014\nposte : analyste fonctionnelle ti - moa\nprojet signatures et pouvoirs : une délégation de signature est un acte juridique par lequel une autorité , le déléguant , délègue non pas ses\npouvoirs , mais la faculté de signer des documents et actes énumérés strictement dans la délégation à une tierce personne\nrecueillir les informations d ' affaires\nrevue de mise en place du site avec les développeurs\nrédaction des cas d ' utilisation et modélisation uml\nenvironnement technique : rational rose ibm , uml , cmmi\nle crédit lyonnais ( mandat cabinet aubay )\noctobre 2013 à juin 2014\nposte : analyste d ' affaires ( pilier risque ) - moa\nprojet lcl pilotage du risque l ' application lcl risques permet le pilotage des risques pour la banque des particuliers et la direction des\nservices banques assurances . il s ' agit de remonter les risques , au moyen d ' indicateurs , aux acteurs du réseau et leur permettre d ' établir des\nplans d ' actions à l ' aide de reportings\nencadrer la clientèle dans l ' expression de besoin de leurs besoin d ' affaires\ncoordonner la planification du projet avec les développeurs et le client\nrédaction des besoins et les exigences d ' affaires dans des documents structurés et complet\nrédaction de la stratégie de test et mise en place de jeu d ' essai\nanalyser et réviser les stratégies de gestion du changement et de communication\nreprésenter l ' analyste d ' affaires durant les différents comités\nformation de l ' utilisateur à l ' outil lcl risques et rédaction des guides utilisateurs\ncontrôler le respect de la restitution des indicateurs lcl risques\nenvironnement technique : access , excel , bo ( business object ) , mantis , sql\ncompétences techniques\nbase de données : sql server , mysql , db2 , natural database\nméthode d ' analyse : uml , merise méthodes agile : scrum , kanban , pspo en cours\nlangages : cobol , natural , pacbase , jcl , langage de balisage os : windows z / os : cics\nprogiciel de gestion : office microsoft , sharepoint , openlink , mega , ms project , visio , quality center , mantis ,\nbusiness object , ibm rational rose , jira , jenkins , bitbucket\netudes et titres\ndiplôme d ' ingénieur en système information et génie logiciel , ecole ingesup , paris ( france )\nlicence informatique de gestion option développeur d ' applications , ecole ectei , paris ( france )\ndec action communication commercial , ecole henry wallon , aubervilliers ( france )\nlangues\nanglais : courant\nfrançais : langue maternelle\npage 2 sur 2\nfrançais :langue maternelle anglais :courant",
        "experiences_duration": 5.6447862760019998,
        "educations_duration": 0,
        "experiences": [
            {
                "key": "3bd7a3e409abd073dd29a9134d33348e35a9ee51",
                "title": "Analyste d'affaires",
                "description": "Livraison des solutions web transactionnels"
                "location": {
                    "text": "Montreal, QC, Canada",
                    "lat": 45.512410000000003,
                    "lng": -73.554689999999994,
                    "gmaps": null,
                    "fields": []
                },
                "date_start": "2017-08-01T00:00:00",
                "date_end": "1969-12-31T23:59:59",
                "hard_skills": [],
                "soft_skills": [],
                "company": "Banque Nationale"
            }
        ],
        "educations": [
            {
                "key": "key",
                "title": "Developper",
                "description": "Web Developpement",
                "location": {
                    "text": null,
                    "lat": null,
                    "lng": null,
                    "gmaps": null,
                    "fields": []
                },
                "date_start": null,
                "date_end": null,
                "hard_skills": [],
                "soft_skills": [],
                "school": null
            }
        ],
        "attachments": [],
        "skills": [
            {
                "name": "UML",
                "value": "hard",
                "type": null
            },
            {
                "name": "Merise",
                "value": "hard",
                "type": null
            },
            {
                "name": ": CICS",
                "value": "hard",
                "type": null
            }
        ],
        "languages": [],
        "interests": [],
        "labels": [],
        "tags": [
            {
                "name": "archive",
                "value": false
            }
        ],
        "metadatas": []
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```bash
{
    "code": 400,
    "message": "Invalid source fields"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Example

{% tabs %}
{% tab title="Python" %}
```python
from hrflow import Hrflow

client = Hrflow(api_secret="Your API Key", api_user="Your API user email")

client.profile.indexing.get(source_key="source_key",
                            key="profile_key",
                            # OR
                            reference='profile_reference',
                            # OR
                            email='example@example.com')
```
{% endtab %}

{% tab title="Javascript" %}
```javascript
import Hrflow from 'hrflow';

const client = new Hrflow({ 
    api_secret: 'Your API Key',
    api_user: 'Your API user email' 
});

client.profile.indexing.get('source_key', {
    key: 'profile_key',
    // or
    reference: 'profile_reference'
    // or
    email: 'example@example.com',   
}).then(response => {
    console.log(response);
    // ...
});
```
{% endtab %}
{% endtabs %}

