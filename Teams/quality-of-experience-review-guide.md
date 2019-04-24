---
title: Guide d’Analyse de la Qualité d’Expérience pour Microsoft Teams
author: rmw2890
ms.author: rowille
manager: serdars
ms.date: 09/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Guide pour l’analyse des performances de médias en temps réel pour Microsoft Teams à l’aide du tableau de bord de la qualité des appels (CQD).
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e85d6e44c37b1b7a56b2b525d28fdbeab266d4b8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211287"
---
# <a name="quality-of-experience-review-guide"></a>Guide d’examen de l’expérience de qualité

<!-- Note that this link to the Word doc is intentionally NOT the aka.ms/qerquide link -->
Ce guide est à la phase de valeur lecteur pour Microsoft Teams et Skype pour Business Online. Vous pouvez [télécharger une version de Word](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) de ce guide.

## <a name="introduction"></a>Introduction

Pour que le plus grand impact sur l’amélioration de l’expérience utilisateur, les organisations doivent mettre les zones clés qui sont indiquées dans la figure suivante. Des zones supplémentaires incluent identifiant les tâches opérationnelles, établir les objectifs de mesures de qualité, déterminer les mesures à utiliser pour évaluer le succès de l’organisation et limiter les zones d’enquête selon vos besoins.


![Clé pour la qualité de l’expérience utilisateur concernent audio, la fiabilité, les enquêtes effectuées auprès, clients et appareils.] (media/qerguide-image-keyareas.png "Clé pour la qualité de l’expérience utilisateur concernent audio, la fiabilité, les enquêtes effectuées auprès, clients et appareils.")

_Figure 1 : zones opérationnelles clé couvertes dans ce guide_

En permanence évaluer et corriger les zones décrites dans ce guide, vous pouvez réduire leur potentiel pour un impact négatif sur la qualité de l’expérience de vos utilisateurs. La plupart des problèmes d'expérience utilisateur rencontrés lors d'un déploiement peuvent être regroupés dans les catégories suivantes :

-   Configuration incomplète du pare-feu ou du proxy
-   Faible couverture Wi-Fi
-   Bande passante insuffisante
-   VPN
-   Pilotes et les versions du client incohérents ou obsolètes
-   Périphériques audio non optimisées ou intégrés
-   Sous-réseaux ou périphériques réseau problématiques

Via une planification et conception avant de déployer des équipes ou Skype pour Business Online, vous pouvez réduire le volume de travail qui est requis pour maintenir une expérience de haute qualité.

Ce guide se concentre sur l’utilisation en ligne du tableau de bord de la qualité des appels (CQD) comme le principal outil pour signaler et examiner chaque zone, avec un accent sur son adoption et impact. Les améliorations apportées au réseau pour améliorer l’expérience audio auront également directement des améliorations dans le partage du bureau et vidéo.

Pour accélérer votre évaluation, [deux modèles CQD curated](https://aka.ms/qertemplates) sont fournies : une pour la gestion de tous les réseaux, l’autre est filtré pour les réseaux (internes) gérés. Bien que les modèles de rapport de tous les réseaux sont configurés pour afficher des informations de réseau et de création, ils peuvent toujours utilisés pendant que vous travaillez vers la collecte et de chargement des informations de construction. Téléchargement d’informations en CQD permet au service améliorer la création de rapports en ajoutant les informations de création, le réseau et emplacement personnalisées lors de la différenciation interne à partir de sous-réseaux externes. Pour plus d’informations, voir [mappage de création](#building-mapping) plus loin dans ce guide.

### <a name="intended-audience"></a>Audience ciblée

Ce guide est destiné à être utilisé par les parties prenantes de partenaires et des clients avec les rôles de Collaboration/architecte en chef, Consultant, spécialiste des modifications gestion / d’Adoption, entraîner de support technique, câble réseau, bureau conduire et administrateur informatique

Ce guide est également destiné à être utilisé par le champion(s) qualité désignés. Pour plus d’informations, voir [le rôle Champion de qualité](4-envision-plan-my-service-management.md#the-quality-champion-role).

## <a name="prerequisites"></a>Conditions requises

Avant d’utiliser ce guide, assurez-vous que vous avez le client appropriée les [rôles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) affectés afin que vous puissiez accéder CQD.

-   **Rôle d’administrateur général Office 365** 

-   **Skype pour le rôle d’administrateur** 

-   **Rôle d’administrateur de Service équipes** 

-   **Rôle de Communications ingénieur du Support technique d’équipes** 

-   **Rôle de spécialiste prise en charge des Communications d’équipes** 

Autrement, vous pouvez affecter le rôle suivant à un compte d’utilisateur Office 365 pour autoriser l’accès aux fonctionnalités de création de rapports uniquement.

-   **Rapports lecteur :** Peuvent afficher tous les [rapports d’activité](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) dans le centre d’administration Office 365, les rapports à partir du [pack de contenu Office 365 Adoption](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)et des rapports CQD.

## <a name="what-is-quality"></a>Quelle est la qualité ?

Lorsque vous abordez qualité dans Skype pour les entreprises et les équipes, il est important de définir le terme pour obtenir une présentation courants. Qualité, tel que défini ici, est une combinaison de l’expérience utilisateur et de mesures de service.

<!-- Note: need to update graphic-->
Mesures de Service ![sont composés de ratio flux médiocre, la fiabilité, points de terminaison/les appareils et les versions du client. L’expérience utilisateur est composée de la perception de l’utilisateur de la qualité du service.] Mesures de Service (media/qerguide-image-whatisquality.png "sont composés de ratio flux médiocre, la fiabilité, points de terminaison/les appareils et les versions du client. L’expérience utilisateur est composée de la perception de l’utilisateur de la qualité du service.")

_Figure 2 : quelle est la qualité ?_

### <a name="service-metrics"></a>Mesures de service

Mesures de service se composent des mesures de basée sur le client spécifique. Au cours de chaque appel, le client collecte des informations sur l’appel de télémétrie et envoie un rapport à la fin de chaque appel ultérieurement accessibles via CQD ou [Analytique appeler](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309). Ces mesures sont les suivantes :

-   Taux de flux médiocre
-   Taux d’échec du programme d’installation
-   Taux d’échec de dépôt


#### <a name="poor-stream-rate"></a>Taux de flux médiocre

Le taux de flux médiocre (qui) représente le pourcentage global de l’organisation de flux de données de qualité médiocre. Cette mesure vise à mettre en surbrillance les zones où votre organisation peut se concentrer afin d’affecter le plus élevé en réduisant cette valeur et améliorer l’expérience utilisateur, c’est pourquoi [les réseaux gérés](#managed-vs-unmanaged-networks) sont le principal objectif lorsque vous examinez les régions déterminées. Les utilisateurs externes sont trop importants, mais diffère d’enquête sur une base d’organisation. Envisager de renvoyer des meilleures pratiques pour les utilisateurs externes et recherchez les appels externes indépendamment de l’entreprise globale.

La mesure réelle en CQD selon la charge de travail, mais à des fins de l’examen de l’expérience de qualité nous concentrer principalement sur la mesure _Audio médiocre pourcentage_ . QUI se compose des cinq moyennes métrique réseau décrites dans le tableau suivant. Pour un flux être classé comme médiocre, qu’une mesure doit dépasse le seuil défini. Pour plus d’informations sur le processus de classification des flux de données, consultez [cet article](stream-classification-in-call-quality-dashboard.md).

> [!Note]
> CQD fournit la « … dû à une mauvaise » des mesures de mieux comprennent de quelle condition a provoqué le flux classées comme médiocres.


_Tableau 1 : mesures de qualité Audio_

| Moyenne de métrique     | Description     | Expérience utilisateur |
|-------------|-----------------|-----------------|
| Gigue \>30 ms        | Il s’agit de la variation moyenne de retard entre les paquets successives. Les équipes et Skype pour les entreprises peuvent s’adapter à certains niveaux de gigue par le biais de mise en mémoire tampon. Il est uniquement lorsque la gigue dépasse la mise en mémoire tampon un participant d’avertissements les effets de gigue.      | Les paquets arrivant à différentes vitesses provoquent voix d’un haut-parleur à son automatisée.   |
| Taux de pertes de paquets \>0,1 ou 10 %        | Il est souvent définie sous forme de pourcentage des paquets sont perdus. Perte de paquets affecte directement la qualité audio, à partir de petite, individuel paquets perdus qui n’ont presque aucun impact pertes rafale DOS à DOS que la fonctionnalité audio cause découper complètement.     | Les paquets en cours perdus et d’arriver pas à leur destination entraîner des écarts dans le support, qui en résulte dans des mots et syllabes manqués et saccadé vidéos et de partage. |
| Temps d’aller-retour \>500 ms        | Il s’agit du temps que nécessaire pour obtenir un paquet IP à partir d’un point à point B et au point A. Ce délai de propagation de réseau est lié à la distance physique entre les deux points et la vitesse de la lumière et inclut une surcharge supplémentaire prise par les différents périphériques dans le chemin d’accès réseau.      | Les paquets prend trop de temps pour parvenir à sa destination provoquent un effet talkie-walkie.   |
| Moyenne de dégradation NMOS \>1.0         | Dégradation de [Réseau moyenne d’avis Score (NMOS)](https://docs.microsoft.com/previous-versions/office/communications-server/bb894481(v=office.12)#network-mos) moyenne pour le flux. Représente la quantité la perte de réseau et la gigue a affecté la qualité de l’audio reçu qui a provoqué le NMOS à déplacer en plusieurs points. | Il s’agit d’une combinaison de gigue, la perte de paquets, et, dans une moindre mesure : augmenter le temps d’aller-retour. L’utilisateur peut être confronté à une combinaison de ces problèmes.   |
| Taux moyen d’échantillons \>7 % ou 0,07 | Taux moyen d’un nombre de trames audio avec échantillons masqués générés par la perte de paquets correcteur et le nombre total d’images audio. Un échantillon audio masqué est une technique utilisée pour atténuer les la transition brutale doit généralement être provoquée par paquets perdus.      | Des valeurs élevées indiquent que des niveaux significatifs de masquage de perte ont été appliquées et a provoqué audio déformé ou perdue.     |

#### <a name="setup-failure-rate"></a>Taux d’échec du programme d’installation

Le taux d’échec du programme d’installation, également appelé la mesure _Nombre Total pourcentage d’échec du programme d’installation d’appel_ dans CQD, est le nombre de flux de données où le chemin d’accès des médias n’a pas pu être établie entre les points de terminaison au début de l’appel.

Représente n’importe quel flux multimédias qui n’ont pas pu être établie. La gravité de l’impact sur l’expérience utilisateur mesurée ici, l’objectif consiste à réduire cette valeur comme proches de zéro que possible. Une valeur élevée pour cette mesure est plus fréquente dans les nouveaux déploiements avec des règles de pare-feu incomplète qu’un déploiement évolué, mais il est important de regarder régulièrement.

Cette mesure est calculée en prenant le nombre total de flux de données n’a pas pu configurer divisée par le nombre total de flux de données envoyé un enregistrement de détail appel réussi (CDR) :

-   **Taux d’échec de configuration** = appel Total du programme d’installation de nombre de flux de données ayant échoué / Stream, nombre Total CDR disponibles

#### <a name="drop-failure-rate"></a>Taux d’échec de dépôt

Le taux de défaillance, également appelé la mesure _Total appel rejeté pourcentage d’échec_ dans CQD, est le pourcentage de flux correctement établies, où le chemin d’accès des médias n’a pas se terminer normalement.

Représente n’importe quel flux multimédias qui s’est arrêté inopinément. Bien que l’impact de ce n’est pas aussi grave en tant que flux ayant échoué pour configurer, il va compromettre l’expérience utilisateur. Projections multimédia soudaines et fréquents seulement peuvent avoir un impact grave sur l’expérience utilisateur, ils entraînent le besoin pour les utilisateurs à se reconnecter, entraînant une perte de productivité.

La mesure est calculée en prenant le nombre total de flux ignorés divisée par le nombre total de flux de données qui a été configuré correctement :

-   **Déplacer le taux d’échec** = Total appel abandonné flux Count / nombre Total d’appels le programme d’installation a réussi nombre de flux

### <a name="define-your-target-metrics"></a>Définir votre mesures cible

Cette section décrit quelques-unes des mesures service principaux que nous utilisons pour évaluer comment services expérience d’intégrité. En évaluant et conduite efforts de garder ces mesures ci-dessous leurs destinations définies à en permanence, vous allez assurer que vos utilisateurs rencontrent la qualité des appels de façon cohérente et fiable. Pour vous aider, les objectifs suivants sont fournis.

_Tableau 2 - mesures d’évaluation principaux cible d’intégrité_
<table>
<tr>
<th rowspan="2" colspan="2" valign="center">Type de réseau</th><th rowspan="1">Objectifs de qualité</th><th colspan="2">Objectifs de fiabilité</th></tr>
<tr><th>Taux de flux de données audio médiocre</th><th>Taux d’échec du programme d’installation</th><th>Taux d’échec de dépôt</th></tr>
<tr><td rowspan="2"><strong>All</strong></td><td>Interne</td><td>2.0 %</td><td>0,5 %</td><td>2.0 %</td></tr>
<tr><td>Global</td><td>3.0 %</td><td>1,0 %</td><td>3.0 %</td></tr>
<tr><td rowspan="5"><strong>Conférence</strong></td><td>Interne</td><td>2.0 %</td><td>0,5 %</td><td>2.0 %</td></tr>
<tr><td>Filaire interne</td><td>1,0 %</td><td>0,5 %</td><td>1,0 %</td></tr>
<tr><td>Wi-Fi 5 GHz interne</td><td>1,0 %</td><td>0,5 %</td><td>1,0 %</td></tr>
<tr><td>Wi-Fi 2,4 GHz interne</td><td>2.0 %</td><td>0,5 %</td><td>2.0 %</td></tr>
<tr><td>Global</td><td>2.0 %</td><td>0,5 %</td><td>3.0 %</td></tr>
<tr><td rowspan="4"><strong>P2P</strong></td><td>Interne</td><td>2.0 %</td><td>0,5 %</td><td>2.0 %</td></tr>
<tr><td>Filaire/Wi-Fi 5 GHz interne</td><td>1,0 %</td><td>0,5 %</td><td>1,0 %</td></tr>
<tr><td>Filaire/Wi-Fi 5 GHz globale</td><td>2.0 %</td><td>1,0 %</td><td>1,0 %</td></tr>
<tr><td>Global</td><td>2.0 %</td><td>1,0 %</td><td>3.0 %</td></tr>
</table>


Il est important de discuter et définir les objectifs de votre organisation pour répondre aux objectifs de votre entreprise.

### <a name="user-experience"></a>Expérience utilisateur

Analyse de l’expérience utilisateur est plus art qu’une science, les mesures collectées ici ne toujours parce qu’il existe un problème avec le réseau ou le service, mais plutôt qu’ils indiquent simplement que l’utilisateur détecte un problème. Microsoft propose un mécanisme d’enquête intégrée — connus en tant que taux mon appel (RMC) — pour aider à évaluer l’expérience utilisateur globale. RMC va vous aider à répondre aux questions suivantes à partir du point de vue de vos utilisateurs :

-   Savoir comment utiliser la solution ?
-   Est la solution facile à utiliser et intuitive, et ne prend en charge mes besoins en communication quotidienne ?
-   Est la solution m’aider à faire mon travail ?
-   Quel est mon perception globale de la solution ?
-   Puis-je utiliser la solution à tout moment dans le temps, quel que soit l’où je suis ?
-   Puis-je configurer et maintenir un appel ?

#### <a name="rate-my-call"></a>Taux de mon appel 

Taux de mon appel (RMC) est intégré dans les équipes et Skype pour les entreprises et est automatiquement configuré pour être affiché pour le participant après 1 dans tous les 10 appels ou 10 pour cent. Ce bref questionnaire invite l’utilisateur à évaluer l’appel et fournissent un contexte peu pour pourquoi la qualité des appels ont pu médiocre. Une évaluation d’un ou deux est considéré comme une mauvaise, trois ou quatre est correcte et cinq est considérée comme excellente. Bien qu’il soit un peu d’un indicateur à cause du retard, il s’agit d’une mesure utile pour les problèmes découvrant les mesures de service peuvent être manquantes.

> [!Note]
> Jusqu'à ce que les utilisateurs sont formés pour répondre aux enquêtes RMC en donnant une bonne commentaires en plus de réponses incorrects, généralement revenir comme extrêmement négative. La plupart des utilisateurs répondront uniquement lorsque la qualité des appels est faible. Pour cette raison, vos rapports RMC peuvent être oblique sur le côté une mauvaise même si des mesures de service sont corrects.

Vous pouvez utiliser CQD pour créer des rapports sur les réponses de l’utilisateur RMC et exemples de rapports sont inclus dans le modèle CQD. Toutefois, elles ne sont pas présentées en détail dans ce guide. Pour plus d’informations sur RMC dans Skype pour Business en ligne et des conseils pour la formation des utilisateurs donner des réponses RMC utiles, voir [ce billet de blog](https://blogs.technet.microsoft.com/jenstr/2015/05/05/rate-my-call-in-skype-for-business-2015/).

#### <a name="client-and-device-readiness"></a>Préparation des clients et périphériques

Vous avez besoin d’une stratégie de client et des périphériques solide pour s’assurer que les utilisateurs disposent d’une expérience utilisateur positive et cohérente. Chaque stratégie de préparation du lecteur quelques principes clés.

##### <a name="client-readiness"></a>Préparation du client

Une stratégie de disponibilité du client fort garantit que vos utilisateurs exécutent la version la plus récente du client tout en profitant le meilleur parti. Microsoft correctifs régulièrement la Skype pour client d’entreprise ; en vous assurant que vous maintenir à jour dans votre environnement est essentiel pour votre réussite globale. Il est également important n’oubliez pas de réseau de correctif, vidéo, USB et pilotes audio, car ils sont souvent ignorés et susceptibles d’affecter l’expérience utilisateur. Envisagez d’ajouter la vidéo en réseau, Wi-Fi, USB et les pilotes audio pour votre processus de gestion des correctifs en cours.

Nous vous recommandons de pas laisser votre versions du client comprises en plus de six mois. Si vous utilisez Office Click-to-Run, vous êtes déjà en cours mis à jour par le service. Utilisez les [versions du client](#client-versions)incluses, comme décrit plus loin dans ce guide, pour vous aider dans ce processus. Vous pouvez également exploiter les exemples de rapports taux mon appel à améliorer votre stratégie de disponibilité du client.

> [!IMPORTANT]
> Actuellement, les équipes clients sont distribués et mis à jour automatiquement via le réseau de livraison de contenu Azure et seront conservés à jour par le service. Par conséquent, préparation des clients et activités investigation ne sont pas applicables aux équipes.


##### <a name="device-readiness"></a>Préparation du périphérique

Aucune une stratégie unique ne peut affecter l’expérience utilisateur plus de votre stratégie de disponibilité du périphérique. La plupart des organisations conviennent supprimer les périphériques inutiles (par exemple, téléphones de bureau ou d’autres périphériques audio dédiés) des utilisateurs, et il s’agit souvent une justification principaux de passage à des équipes ou Skype pour les entreprises. Toutefois, ces organisations même parfois hésitent pas à fournir des périphériques de remplacement, même si ces périphériques sont moins onéreux. Ordinateurs portables moderne et PC, mais équipés de microphone et haut-parleur, intégrés ne sont pas optimisés pour professionnelles voix sur IP (VoIP). Cela crée souvent une mauvaise expérience pour tous les participants, en particulier si le haut-parleur est dans un environnement de bruit. Programme de certification de périphériques de Microsoft garantit que lorsqu’un utilisateur participe à un appel téléphonique à l’aide de n’importe quel appareil certifié pour les équipes ou Skype pour les entreprises, elle génère une expérience est supérieure à un périphérique non certifiés. 

Nous vous recommandons toujours que Skype pour les utilisateurs professionnels et les équipes utilisent un casque certifié ou les haut-parleurs lorsque vous participez à un appel vocal via le client de bureau. Pour plus d’informations sur Microsoft certifié appareils, passez en revue ces articles sur le [programme de certification](/SkypeForBusiness/certification/overview) et afficher le [catalogue des solutions partenaires](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). Utilisez le [rapport de périphériques](#devices), décrites plus loin dans ce guide, pour l’aide à la gestion de vos périphériques.


### <a name="categories-of-quality"></a>Catégories de qualité

La réussite d’un déploiement de haute qualité et fiable à mettre en application dépend de votre rigueur opérationnelles de construction. Plus précisément, une attention particulière aux trois catégories illustré dans la figure suivante ; Il s’agit de l’objectif de ce guide :

-   **Réseau :** Qualité audio axé sur la mesure du taux de flux médiocre (qui), l’utilisation TCP, des sous-réseaux avec et sans fil et l’identification de l’utilisation de VPN et les proxys HTTP.

-   **Points de terminaison :** Périphériques audio et les versions du client (Skype pour les entreprises uniquement).

-   **Gestion des services :** Cette catégorie comprend deux sections :

    -   Tout d’abord incombe de Microsoft pour gérer et tenir à jour les équipes et Skype pour Business Online services.

    -   Deuxième sont les tâches de que votre organisation doit gérer pour garantir un accès fiable au service, telles que la mise à jour des informations de création et maintenance de pare-feu pour le nouvel Office 365 adresses comme infrastructure est ajoutée au service.

![Les catégories de qualité dans une organisation : service de gestion, les systèmes d’extrémité et le réseau.] (media/qerguide-image-categories.png "Les catégories de qualité dans une organisation : service de gestion, les systèmes d’extrémité et le réseau.")

_La figure 3 - catégories critiques pour les équipes et Skype pour le déploiement d’entreprise en ligne_

Le graphique suivant présente les tâches que vous devez exécuter pour chaque catégorie. Nous vous conseillons d’exécuter ces tâches une fois par semaine, au minimum.

La première fois que vous effectuez ces tâches prendra plus d’effort que des itérations suivantes, car la plupart des catégories suivantes nécessitent que vous validez les configurations de votre déploiement. Une fois que vous avez réalisé l’état souhaité en réunion cibles que vous avez définie, exécution de ces tâches vous aideront à mettre à jour cet état.

<!--  This is a net new graphic, never was included in the online article. OOPS! -->
![Liste des tâches hebdomadaires par catégorie de qualité] (media/qerguide-image-tasks.png "Liste des tâches hebdomadaires par catégorie de qualité")

#### <a name="service-management-tasks"></a>Tâches de gestion de service

Dans un environnement cloud d’abord, vous devez effectuer certaines tâches de gestion de service pour maintenir une expérience utilisateur de qualité. Ces tâches comprise, garantissant la bande passante est suffisante pour atteindre le service sans saturer les liaisons internet, validation de qualité de service (QoS) est en place sur tous les domaines de réseau géré, et, enfin, face à [Office 365 IP plages sur pare-feu](https://aka.ms/o365ips).

#### <a name="network-tasks"></a>Gestion du réseau

Il existe deux catégories de gestion du réseau : la fiabilité et la qualité. La fiabilité se concentre sur la mesure de la capacité de l’utilisateur à passer des appels avec succès et restez connecté. Qualité se concentre sur la télémétrie agrégée envoyé aux équipes et Skype pour Business Online par le client de l’utilisateur pendant l’appel et une fois qu’elle est terminée. 

Étant donné l’impact majeur de fiabilité sur l’expérience utilisateur, il est important de commencer à évaluer et rechercher ces mesures avant de plonger dans qualité. 

#### <a name="endpoints-tasks"></a>Tâches de points de terminaison

La principale tâche de cette catégorie valide les versions du client sont en cours d’exécution Skype pour les entreprises sur les builds de bureau à partir d’au cours des six derniers mois, pour garantir les utilisateurs obtiennent l’avantage des optimisations continues apportées à la Skype pour le client de bureau d’entreprise. En outre, simplifie les tâches de gestion globale du client et fournit une expérience utilisateur cohérente.

La zone autres importante est analyse les périphériques sont courants dans votre déploiement et l’utilisation de périphériques certifiés pour fournir la meilleure expérience utilisateur de commande.


> [!IMPORTANT]
> Actuellement, les équipes clients sont distribués et mis à jour automatiquement via le réseau de livraison de contenu Azure et seront conservés à jour par le service. Préparation des clients et activités investigation ne sont pas applicables aux équipes.

## <a name="cqd-basics"></a>Notions de base CQD

Cette section décrit les concepts fondamentaux de l’utilisation de CQD. Est fournie pour les rubriques suivantes :

-   What ' s CQD ?
-   Attentes à l’aide de CQD
-   Recherche de votre ID client
-   Création de rapports sur les équipes Microsoft et Skype pour les entreprises
-   Première et deuxième classifications
-   Mesures, dimensions et des filtres
-   Flux de données par rapport à des appels
-   Appels non classés, bonne et médiocres
-   Sous-réseaux courantes

Pour plus de formations et de ressources, voir l' [annexe](#other-resources).

### <a name="what-is-cqd"></a>What ' s CQD ?

Le tableau de bord de qualité des appels (CQD) vous permet de comprendre la qualité des appels effectués à l’aide des équipes et Skype pour les services. CQD est conçu pour aider à Skype pour les administrateurs d’entreprise et les équipes et les ingénieurs réseau optimiser le réseau et garder un œil sur la qualité, la fiabilité et l’expérience utilisateur. CQD examine télémétrie agrégation pour toute une organisation où les modèles globales peuvent devenir apparentes, ce qui permet au personnel informé évaluer et planifier les activités de correction pour optimiser l’impact. CQD fournit des rapports de mesures qui fournissent un aperçu de la qualité, la fiabilité et l’expérience utilisateur.

> [!Note]
> CQD ne contient pas les informations d’identification personnelle (PII). Informations d’identification personnelle sont informations pouvant être utilisées sur son propre ou avec d’autres informations pour identifier, de contacts ou de localiser une seule personne, ou pour identifier une personne dans le contexte.

Ce guide vous aide à comprendre les concepts de base de CQD pour optimiser l’impact que vous permettent d’améliorer l’expérience de vos utilisateurs avec des équipes ou Skype pour Business Online. Vous trouverez des ressources CQD supplémentaires dans l' [annexe](#other-resources).

### <a name="expectations-using-cqd"></a>Attentes à l’aide de CQD

CQD, bien qu’utiles pour l’analyse des tendances et les sous-réseaux, ne fournit toujours une cause spécifique pour un scénario donné. Il est important de comprendre ce et définir l’attente correct lors de l’utilisation de CQD :

-   CQD ne vous fournira la cause de chaque scénario.
-   Flux de données système téléphonique ou de conférence Audio ne contient pas CQD.
-   CQD appelle les zones examinés basés sur les tendances.
-   CQD ne contient pas les informations d’identification personnelle.

### <a name="report-editions"></a>Éditions de rapport

Il existe deux éditions de rapport dans CQD en ligne : résumé et détaillé. Utilisez le menu déroulant situé dans la barre de bleue dans la partie supérieure de l’écran pour ouvrir une édition de rapport. Le nom de l’édition de rapport sélectionné est affiché dans la partie supérieure de l’écran.

-   Rapports de synthèse sont statiques et ne peuvent pas être modifiés, téléchargé ou exporté. 
-   Rapports détaillés sont entièrement personnalisables et peuvent être téléchargés dans un fichier CSV, exporté ou cloné.

Pour obtenir une description complète de la différence entre les deux éditions, consultez [cet article](turning-on-and-using-call-quality-dashboard.md).

![Menu déroulant avec des rapports de synthèse sélectionné](media/qerguide-image-reportcategories.png)

_La figure 4 - catégories de rapport CQD_

Les rapports de synthèse sont divisées en quatre catégories :

-   **Rapports de synthèse** le focus sur l’analyse des tendances de qualité avec tous les jours, tous les mois et les rapports de tableau pour vous aider à identifier les sous-réseaux de qualité médiocre. Il s’agit de la page d’accueil par défaut lors de votre première connexion à CQD en ligne.
-   **Rapports Location-Enhanced** le focus sur l’analyse des tendances de qualité en fonction des informations d’emplacement. Pour utiliser ces rapports, vous devez avoir téléchargé un fichier construction.
-   Focus de **La fiabilité des rapports** sur l’analyse des tendances de fiabilité pour (VBSS) partage d’écran vidéo audio, vidéo et partage d’application.
-   **Rapports de qualité de l’expérience** sont une version « épurée » des modèles QER détaillées, en mettant l’accent sur les zones clés pour l’analyse de la fiabilité et la qualité audio.

### <a name="report-types"></a>Types de rapports

Vous pouvez choisir parmi deux types de rapports dans CQD, selon la façon dont vous souhaitez afficher vos données. Bien que ce guide n’aborde les caractéristiques de la création d’un type de rapport sur un autre, les modèles QER CQD fournissent un mélange de rapports de graphique et tableau personnalisables pour pouvoir utiliser :

-   Les rapports de graphique créer des graphiques barre pour représenter les données dans un format visuel. Les rapports de graphique sont adaptés à la visualisation des données sur une période donnée.
-   Rapports de tableau sont utiles pour consulter des dimensions et mesures spécifiques lorsque vous exportez les rapports dans un fichier CSV pour la manipulation dans Microsoft Excel.

### <a name="tenant-id"></a>ID de client

Certains rapports CQD nécessitent que vous incluez un filtre pour votre ID de client. En raison de la manière de que CQD regroupe les données télémétrie participant fédéré est inclus. Bien que cela peut s’avérer utile lors de l’analyse des tendances, des rapports client et des périphériques nécessitent que vous filtrez les données pour un client spécifique à exclure télémétrie participant fédéré. Si vous ne connaissez pas votre ID client, vous pouvez utiliser une des méthodes suivantes pour le trouver.

> [!Note]
> Ces méthodes nécessitent les autorisations suivantes :<ul><li>Rôle d’administrateur global</li><li>Skype pour le rôle d’administrateur</li></ul>

#### <a name="azure-portal"></a>Portail Azure

1.  Connectez-vous au portail Microsoft Azure :<https://portal.azure.com>

2.  Sélectionnez **Azure Active Directory**.

3.  Sous **Manage**, sélectionnez **Propriétés**. L’ID client est indiqué dans la zone **ID de répertoire** .

#### <a name="azure-powershell"></a>Azure PowerShell

1. [Installer le module de gestion des services Microsoft Azure PowerShell](https://docs.microsoft.com/powershell/azure/servicemanagement/install-azure-ps?view=azuresmps-4.0.0).

2. Ouvrez une fenêtre de commande Windows Azure PowerShell et exécutez le script suivant, entrez vos informations d’identification Office 365 à l’invite : 

   ```
   Login-AzureRmAccount
   ```

3. L’ID de client est répertorié dans la sortie.

#### <a name="skype-for-business-online-admin-center"></a>Skype Business Online Centre d’administration

1.  Accédez à <https://portal.office.com>.

2.  Connectez-vous avec votre compte d’administrateur client d’organisation.

3.  Sélectionnez **Skype pour les entreprises** sous **Centres d’administration**.

4.  L’ID de client est répertorié en tant **qu’ID de l’organisation** sur la page d’accueil.

#### <a name="skype-for-business-online-using-powershell"></a>Skype pour Business Online à l’aide de PowerShell

1. [Configurer votre ordinateur pour Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

2. Exécutez la commande suivante :

   ```
   (Get-cstenant).tenantid
   ```

3. L’ID de client est affiché sous forme de GUID.

### <a name="teams-vs-skype-for-business"></a>Équipes et Skype pour les entreprises

CQD peut créer des rapports sur les équipes et Skype pour télémétrie Business. Toutefois, il peut arriver que lorsque vous souhaitez développer un rapport d’examiner télémétrie équipes distinct Skype pour les entreprises.

#### <a name="summary-reports"></a>Rapports de synthèse

Pour modifier la page de rapports de synthèse pour consulter uniquement les équipes ou Skype pour les entreprises, sélectionnez le menu déroulant de **Filtre de produit** à partir du haut de l’écran, puis sélectionnez le produit que vous souhaitez.

![Menu déroulant affichant l’option de filtrage des rapports CQD par charge de travail](media/qerguide-image-productfilter.png)

_La figure 5 - sélectionner un filtre de produit_

#### <a name="detailed-reports"></a>Rapports détaillés

Pour filtrer tous les rapports détaillés, dans la barre du navigateur, ajoutez le code suivant à la fin de l’URL :

```
/filter/[AllStreams].[Is Teams]|[FALSE]
```

**Exemple :**

```https://cqd.lync.com/cqd/#/1234567/2018-5/filter/[AllStreams].[Is Teams]|[FALSE]```

Pour plus d’informations sur les filtres d’URL, voir [filtrage des rapports](#filtering-reports) plus loin dans cette section.

Pour filtrer un rapport détaillé individuel, ajoutez le filtre ``Is Teams`` à l’état et affectez-lui la valeur True ou False. Pour plus d’informations, consultez [modification des rapports](#editing-reports) plus loin dans cette section.

![Ajouter un filtre à un rapport détaillé.](media/qerguide-image-addteamsfilter.png)

_Figure 6 : ajout d’un filtre Teams Microsoft à un rapport_


### <a name="managed-vs-unmanaged-networks"></a>Réseaux non managées et non managées

Par défaut, tous les points de terminaison dans CQD sont classées comme externe. Dès qu’un fichier construction est introduit, nous pouvons commencer à consulter les données du point de terminaison géré. Comme indiqué précédemment, les réseaux dans CQD sont définis en tant que :

-   _Gérées réseau_, souvent appelé interne ou à l’intérieur, pouvant être influencée et contrôlés par l’organisation. Cela inclut le réseau interne, le réseau étendu à distance et VPN.
-   Un _réseau non géré_, souvent appelé externe ou à l’extérieur, ne peuvent pas être influencé ou contrôlé par l’organisation. Un exemple d’un réseau non géré est un réseau d’hôtel ou un aéroport.

### <a name="dimensions-measures-and-filters"></a>Mesures, dimensions et des filtres

Une requête CQD correcte contienne les trois paramètres suivants :

-   **Dimension :** Comment faire sur les données de tableau croisé dynamique.

-   **Mesure :** Je veux créer un rapport.

-   **Filtre :** Je veux comment réduire le jeu de données de la requête renvoie.

Une autre façon de concevoir le système est qu’une _dimension_ est la fonction de regroupement, une _mesure_ est les données que m’intéresse, et un _filtre_ , c’est comment limiter les résultats à ceux qui sont pertinents pour ma requête.

Un exemple de requête correct est **me faire une mauvaise flux [mesurent] par sous-réseau [Dimension] construction 6 [filtre]**. Pour plus d’informations, voir [Dimensions et mesures disponibles dans CQD](https://aka.ms/cqd-dm).

### <a name="first-vs-second"></a>Première et deuxième 

La plupart des dimensions et mesures CQD sont classées comme première ou deuxième. CQD n’utilise pas de champs de l’appelant/appelé, ils ont été renommées _premier_ et _deuxième_ car il existe des étapes intermédiaires entre l’appelant et l’appelé. La logique suivante détermine l’extrémité impliqués intitulée en tant que premier :

-   **Premier** sera toujours un point de terminaison de serveur (serveur de conférence, le serveur de médiation et ainsi de suite) si un serveur est impliqué dans le flux ou d’un appel.

-   **Deuxième** sera toujours un point de terminaison client, sauf si le flux est entre deux points de terminaison de serveur.

-   Si les deux points de terminaison sont le même type, le choix d’est la première est basé sur le classement interne de la catégorie de l’agent utilisateur. Cela garantit la cohérence de l'organisation.

Pour plus d’informations sur la détermination de la première ou deuxième point de terminaison lorsqu’ils sont identiques, voir [Dimensions et mesures disponibles dans CQD](https://aka.ms/cqd-dm).

### <a name="stream-vs-call"></a>Flux de données et l’appel

Vous devez comprendre la différence entre un appel et d’un flux correctement choisir lequel les dimensions ou mesures vous examinerons dans CQD. Bien que le focus principal du CQD sur les flux, appel en fonction de mesures sont également disponibles.

-   **Flux :** Il existe un _flux_ entre deux points de terminaison. Il existe un seul flux pour chaque direction et deux flux sont requis pour la communication. Flux de données est utiles pour examen aux bâtiments, les réseaux ou sous-réseaux. Dans certains cas, appel et flux sont utilisés dans le nom de la mesure (par exemple, flux de configuration des appels ou appel ignorés flux). Ils sont toujours classés en tant que flux.

-   **Appel :** Un _appel_ est un regroupement de tous les flux de tous les participants. Un appel se compose de : au minimum, deux flux. Un seul appel aura au moins deux points de terminaison, chacun avec un minimum d’un flux de données.

Pour obtenir des instructions supplémentaires sur si la dimension ou mesure fait référence à un appel ou un flux de données, voir [Dimensions et les mesures disponibles dans CQD](https://aka.ms/cqd-dm)

### <a name="good-poor-and-unclassified-calls"></a>Appels non classés, bonne et médiocres

Un appel est classé comme bonne, mauvaise, soit non classés. Prenons un moment pour parler plus en détail chacune d’elles.

-   **Bonne ou mauvaise :** Un appel de bonne ou mauvaise se compose d’un appel qui contient un ensemble complet des mesures de service, pour lequel un rapport QoE complet a été généré et reçu par le service. Pour déterminer si un flux est une bonne ou une mauvaise est décrit [plus haut dans ce guide](#poor-stream-rate).

-   **Non classés :** Un flux non classé ne contient pas un ensemble complet des mesures de service. Il peut s’agir des appels courtes — généralement inférieure à 60 secondes — où moyennes n’ont pas pu être calculées et un rapport QoE n’a pas été créé. Le plus souvent pour les appels à non classés est qu’il y a peu, voire aucune l’utilisation des paquets. Un exemple de ce serait un participant qui se joint à une réunion sur Muet et parle jamais. Le participant est réception, mais ne pas transmettre, multimédia. Sans media transmises, il ne peuvent pas être des mesures CQD à utiliser pour classer les flux de médias sortant du point de terminaison.

Pour plus d’informations sur le processus de classification des flux de données, consultez [cet article](stream-classification-in-call-quality-dashboard.md).

### <a name="common-subnets"></a>Sous-réseaux courantes

Sous-réseaux courantes sont des sous-réseaux privées spécifiques qui sont utilisés par les hôtels, réseau domestique, zones et zones similaires. Ces sous-réseaux est difficiles à triage en raison de leur utilisation généralisée. Si votre organisation utilise une de ces sous-réseaux courants, nous vous recommandons de déplacer ce réseau vers un autre sous-réseau. Cela permettra de création de rapports plus facilement dans CQD. Lorsque le contraire, les rapports dans le modèle de tous les réseaux ont été configurés pour exclure les sous-réseaux pour les supprimer en tant que source de qualité médiocre. Sous-réseaux courantes sont définis ci-dessous ; leur impact varie par l’organisation.

-   10.0.0.0/24
-   192.168.0.0/24
-   192.168.1.0/24
-   192.168.2.0/24
-   172.20.10.0/24
-   192.168.43.0/24

Lorsque vous recherchez un réseau géré qui utilise un sous-réseau courants, vous devez utiliser la dimension de la deuxième adresse IP locale réflexive vers les sous-réseaux du groupe. Cette dimension contient l’adresse IP publique du point de terminaison.

## <a name="cqd-online"></a>CQD en ligne

Cette section décrit les notions de base d’accès aux CQD. Est fournie pour les rubriques suivantes :

-   Accès aux CQD en ligne
-   Mise en route avec CQD
-   Modification de rapports dans CQD
-   Le filtrage des rapports dans CQD
-   Importation de rapports dans CQD

Pour plus de formations et de ressources, voir l' [annexe](#other-resources).

### <a name="access-cqd-online"></a>Accès CQD

Vous pouvez accéder CQD de trois manières :

-   Accédez à <https://cqd.lync.com>.

-   Accédez au **Centre d’administration d’équipes Microsoft** et sélectionnez le lien vers CQD, comme indiqué dans l’illustration suivante.

![Dans le volet de navigation de gauche, le lien vers le tableau de bord de qualité des appels est sélectionné.] (media/qerguide-image-mopo.png "Dans le volet de navigation de gauche, le lien vers le tableau de bord de qualité des appels est sélectionné.")

_La figure 7 – accès CQD via le centre d’administration Microsoft Teams_

-   Accédez à la hérité **Skype pour le centre d’administration de Business** > **Outils**, puis sélectionnez le lien vers CQD, comme indiqué dans l’illustration suivante.

![Outils est sélectionné dans le volet de navigation de gauche, et le lien vers CQD est sélectionné dans le volet principal.] (media/qerguide-image-legacyui.png "Outils est sélectionné dans le volet de navigation de gauche, et le lien vers CQD est sélectionné dans le volet principal.")

_Figure 8 : accès aux CQD via le Skype entreprise centre d’administration_


### <a name="getting-started"></a>Prise en main

Lorsque vous accédez d’abord à CQD, vous verrez la page Rapports de synthèse. La plupart des rapports décrits dans ce guide sont des rapports détaillés personnalisés. Pour commencer à utiliser des rapports détaillés, sélectionnez **Rapports de synthèse** dans la partie supérieure de la page, puis choisissez **Des rapports détaillés**.

![Différents types de rapports disponibles dans CQD](media/qerguide-image-choosereports.png)

_Figure 9 : naviguer vers des rapports détaillés_

La page Rapports détaillés dans CQD ressemble à l’illustration suivante.

![Différents éléments qui constituent un rapport détaillé.](media/qerguide-image-detailedreportspage.png)

|             |           |
| ------------|-----------|
| ![un seul] (media/qerguide-image-callout1.png "un seul") | Le volet Résumé affiche le contexte pour le jeu de rapport qui s’affiche à droite. |
| ![deux] (media/qerguide-image-callout2.png "deux") | Vous pouvez sélectionner **Modifier** dans le volet Résumé pour définir les propriétés au niveau de rapport (y compris la hauteur de l’axe des y) et d’importer de nouveaux modèles. |
| ![trois] (media/qerguide-image-callout3.png "trois") | La barre de navigation permet aux utilisateurs d’identifier leur emplacement actuel dans la hiérarchie du jeu de rapport. |
| ![quatre] (media/qerguide-image-callout4.png "quatre") | Rapports possédant des rapports enfants sont affichés avec un lien bleu. En cliquant sur le lien, vous pouvez accéder à le rapports enfant. |

_Figure 10 : page de rapports détaillés_

Pointez sur les courbes de tendance dans le rapport pour afficher les valeurs détaillées et les graphiques à barres. L’état qui a le focus affiche le menu action : **Modifier**, **Clone**, **Supprimer**, **Télécharger**et **Exporter arborescence du rapport**.

### <a name="editing-reports"></a>Modification de rapports

Lorsque vous sélectionnez **Modifier** dans le menu action d’un état, vous devez ouvrir l’éditeur de requête. Chaque rapport est sauvegardée par une requête pour CQD. Il s’agit de la visualisation des données renvoyées par la requête. L’éditeur de requête est une interface utilisateur pour la modification de ces requêtes outre les options d’affichage pour le rapport, comme illustré dans la figure suivante.

![Différents éléments qui constituent un rapport lorsque le rapport est en cours de modification.](media/qerguide-image-queryeditor.png)

|             |           |
| ------------|-----------|
| ![un seul] (media/qerguide-image-callout1.png "un seul") | Vous choisissez mesures, dimensions et des filtres dans le volet gauche. Pointez sur une valeur existante affiche un bouton Fermer (**X**), que vous pouvez sélectionner pour supprimer la valeur.<ul><li>En sélectionnant la dimension ou mesure, vous pouvez modifier le titre en modifiant le champ **titre** . Vous pouvez également modifier l’ordre en sélectionnant le bleu monter ou Descendre flèches dans le volet supérieur.</li><li>Sélection (**+**) en regard d’un en-tête de la boîte de dialogue pour ajouter une nouvelle dimension, une mesure ou un filtre.</li><li>Entrez les premières lettres de la dimension, une mesure ou un filtre dans la **trouver un** champ pour filtrer la liste de recherche.</li></ul> |
| ![deux] (media/qerguide-image-callout2.png "deux") | Le volet supérieur présente les options de personnalisation de graphique. |
| ![trois] (media/qerguide-image-callout3.png "trois") | L’éditeur de requête affiche un aperçu du rapport. |
| ![quatre] (media/qerguide-image-callout4.png "quatre") | Utilisez la zone **Modifier** au bas de l’écran pour créer ou modifier une description détaillée du rapport. |

_La figure 11 - éditeur de requête_

### <a name="filtering-reports"></a>Le filtrage des rapports

Les modèles fournis incluent plusieurs requêtes intégrées et les filtres du rapport. Les sections suivantes décrivent les filtres les plus courants utilisés dans les modèles.

#### <a name="url-filter"></a>Filtre d’URL

Vous pouvez utiliser une URL de filtrer tous les rapports pour une dimension spécifique. Les filtres d’URL les plus courants sont utilisés pour filtrer les rapports pour exclure télémétrie participant fédéré ou se concentrer sur les équipes ou Skype pour Business Online. Il est recommandé que lors de l’utilisation de filtres, vous signets pour faciliter la référence. 

À l’exclusion de données fédérées à partir des rapports CQD est utile lorsque vous êtes couronnée de bâtiments gérées ou des réseaux où les points de terminaison fédérés peuvent influencer vos rapports.

Pour implémenter un filtre d’URL, dans la barre Adresse du navigateur, ajoutez le code suivant à la fin de l’URL :

```
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Exemple :  

```https://cqd.lync.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]```

Pour filtrer les rapports pour les équipes ou Skype pour les entreprises, ajoutez le code suivant à la fin de l’URL :

```
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

Exemple :

```https://cqd.lync.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Is Teams]|[TRUE]```


> [!NOTE]
> Les exemples d’URL ci-dessus sont pour une représentation visuelle uniquement. Utilisez le lien CQD par défaut de <https://cqd.lync.com>.


#### <a name="query-filters"></a>Filtres de requête

Filtres de requête sont implémentées à l’aide de l’éditeur de requête dans CQD. Ces filtres sont utilisés pour réduire le nombre d’enregistrements renvoyés par CQD, ce qui réduit la taille globale de l’état et les temps de requêtes. Ceci est particulièrement utile pour le filtrage des réseaux non managés. Les filtres répertoriés dans le tableau suivant utilisent des expressions régulières (RegEx).

_Tableau 3 - filtres de requête_

| Filtre         | Description          | Exemple de filtre de requête CQD      |
|----------------|----------------------|-------------------------------|
| Aucune valeur vide   | Certains filtres n’ont l’option de filtrage pour les valeurs vides. Pour filtrer les valeurs vides manuellement, utilisez l’expression vide et la valeur du filtre est égal à ou pas égal à, selon vos besoins.      | Nom de la construction de la seconde \< \> \^ \\s\*\$                       |
| Exclure les sous-réseaux courantes | Sans un fichier construction valide pour séparer gérés à partir de réseaux non gérés, réseau domestique sera inclus dans les rapports. Ces sous-réseaux personnel se trouvent en dehors de l’étendue de son contrôle et peut être exclus rapidement un rapport. Sous-réseaux communs, comme défini dans ce guide, sont 10.0.0.0, 192.168.1.0 et 192.168.0.0. | Deuxième sous-réseau \< \> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Afficher uniquement à l’intérieur  | Utilisé pour filtrer un rapport (interne) managé ou non managé (externe). Le modèle CQD géré est déjà préconfiguré avec ces filtres.       | Seconde à l’intérieur de Corp = à l’intérieur        |

#### <a name="report-filters"></a>Filtres du rapport

Filtres du rapport sont implémentées en ajoutant un filtre pour le rapport rendu soit dans l’éditeur de requête ou directement à l’état. Les filtres de rapport suivants sont utilisés dans le modèle.

_Le tableau 4 - filtres du rapport_

| Filtre     | Description                            | Exemple de filtre de rapport CQD         |
|------------|----------------------------------------|-----------------------------------|
| Month      | Démarrer avec l’année en premier, puis les mois. | 2017-10                           |
| Alphabétique | Filtres pour les caractères alphabétiques. | [a-z]                             |
| Numérique    | Filtres pour n’importe quel caractère numérique.    | [0-9]                             |
| Pourcentage | Filtre un pourcentage.              | ([3-9]\\.) \|([3-9])\|([1-9][0-9]) |

## <a name="import-the-cqd-templates"></a>Importer les modèles CQD

Ce guide inclut [deux modèles CQD curated](https://aka.ms/qertemplates). Ces modèles accélèrent votre utilisation de CQD et vous permettent de rapidement tirer parti des fonctionnalités de CQD un impact sur vos utilisateurs des équipes ou Skype pour une expérience. Le modèle de tous les réseaux, mais optimisé pour fonctionner avec une création de fichier de données, peut être utilisé lorsque vous travaillez à collecter et chargement des informations de construction dans CQD, comme décrit dans la section suivante.

**Pour importer les modèles (. CQDX) en CQD en ligne**

1. Accédez à <https://cqd.lync.com>.

2. Authentification à l’aide de vos informations d’identification d’administration Office 365.

   > [!NOTE]
   > Vous devez disposer d’Office 365 administrateur Global, Skype pour l’administrateur d’entreprise ou rôle lecteurs de rapports accéder aux CQD. 

3. Sélectionnez le menu de **Rapports de synthèse** dans la partie supérieure de la page, puis choisissez **Des rapports détaillés**.

4. Dans le volet Résumé, sélectionnez **Importer**. Accédez à la CQDX enregistré emplacement, sélectionnez le modèle CQDX et sélectionnez **Ouvrir**.

5. Une fois que le modèle est téléchargé, une fenêtre indépendante affiche le message « rapport importation a réussi. » Sélectionnez **OK.**

   ![Notification que le modèle a été correctement importé] (media/qerguide-image-importmessage.png "Notification que le modèle a été correctement importé")

6. Répétez les étapes 4 et 5 pour le deuxième modèle CQD.

> [!NOTE]
> Importer les modèles CQD par utilisateur. Si d’autres utilisateurs doivent utiliser le rapport, ils doivent se connecter et importer les modèles dans leur instance CQD. 


## <a name="building-mapping"></a>Mappage de construction

Dans un équipes ou Skype pour le déploiement d’entreprise en ligne, tous les clients externes. Qui a les conséquences que par défaut, tous les clients sont signalés comme à l’extérieur dans CQD en ligne, quel que soit si le client est connecté sur un réseau d’entreprise interne.

Lorsque vous travaillez avec CQD, vous devez connaître l’emplacement d’un point de terminaison et si elle était connecté à un réseau ou un réseau, vous pouvez gérer les vous ne pouvez pas gérer — l’hypothèse en cours que vous pouvez améliorer les réseaux seulement vous pouvez gérer. En téléchargeant le sous-réseau et les informations de construction sur CQD en ligne, vous activez CQD déterminer si le point de terminaison a été connecté à un réseau d’entreprise/gérées interne ou à un réseau externe/non.

### <a name="building-data-file-structure"></a>Structure de fichier de données de création

Le format du fichier de données que vous téléchargez doit respecter les conditions suivantes pour transmettre le contrôle de validation avant le téléchargement.

-   Le fichier doit être un fichierTSV, ce qui signifie que, pour chaque ligne, chaque colonne est séparée par un caractère de tabulation, ou un fichier CSV dans lequel chaque colonne est séparée par une virgule.

-   Le fichier ne peut pas être supérieur à 50 Mo.

-   Le contenu des données du fichier *ne doit pas inclure les en-têtes de tableau*. En d’autres termes, la première ligne du fichier de données doit correspondre à des données réelles, pas les en-têtes de colonne tels que « Réseau ».

-   Pour chaque colonne, le type de données peut uniquement être Bool, nombre ou chaîne. Si le type de données est un nombre, la valeur doit être une valeur numérique ; s’il est Bool, la valeur doit être 0 ou 1.

-   Pour chaque colonne, si le type de données est la chaîne, les données ne peuvent être vides (mais doivent toujours être séparés par un séparateur approprié — autrement dit, un caractère de tabulation ou une virgule). Cela affecte uniquement ce champ une valeur de chaîne vide.

-   Il doit être 14 colonnes pour chaque ligne. Chaque colonne doit avoir le type de données décrit dans le tableau suivant, et les colonnes doivent être dans l’ordre indiqué dans le tableau.

_Tableau 5 : création de structure de fichier_

| Nom de la colonne        | Type de données | Exemple                   | Aide    |
|--------------------|-----------|---------------------------|-------------|
| Réseau            | String    | 192.168.1.0               | Obligatoire    |
| Nom_réseau        | String    | États-Unis/Seattle/SEATTLE-marin-1 | Obligatoire\*  |
| NetworkRange       | Numéro    | 26                        | Obligatoire    |
| BuildingName       | String    | SEATTLE-MARIN-1             | Obligatoire\*  |
| OwnershipType      | String    | Contoso                   | Facultatif    |
| BuildingType       | String    | Arrêt de l’informatique            | Facultatif    |
| BuildingOfficeType | String    | Ingénierie               | Facultatif    |
| Ville               | String    | Seattle                   | Recommandation |
| ZipCode            | String    | 98001                     | Recommandation |
| Pays            | String    | NOUS                        | Recommandation |
| État              | String    | WA                        | Recommandation |
| Région             | String    | MSUS                      | Recommandation |
| InsideCorp         | Bool      | 1                         | Obligatoire    |
| ExpressRoute       | Bool      | 0                         | Obligatoire    |

\*Alors que ne pas requis par CQD, les modèles sont configurés pour afficher la génération et réseau nom.

#### <a name="supernetting"></a>Création de super-réseaux

Vous pouvez utiliser super-réseaux, généralement appelé inter-Domain Routing (CIDR), à la place de définition de chaque sous-réseau. Un *supernet* est une combinaison de plusieurs sous-réseaux qui partagent un préfixe de routage unique. Au lieu de l’ajout d’une entrée pour chaque sous-réseau, vous pouvez utiliser l’adresse super-réseaux. Super-réseaux est pris en charge, mais nous ne recommandons pas l’utiliser.

Par exemple, construction marketing de Contoso est composée des sous-réseaux ci-dessous :

-   10.1.0.0/24—First étage
-   10.1.1.0/24—second étage
-   10.1.2.0/24—Third étage
-   10.1.3.0/24—Fourth étage

Au lieu de l’ajout d’une entrée pour chaque sous-réseau, vous pouvez utiliser l’adresse super-réseaux — dans cet exemple, 10.1.0.0/22.

-   Réseau = 10.1.0.0
-   Plage réseau = 22

Voici quelques points à prendre en compte avant d’implémenter super-réseaux :

-   Super-réseaux peut être utilisé uniquement dans un mappage de sous-réseau avec masque de bits 28 8 bits.

-   Super-réseaux nécessite moins de temps en amont, mais il s’agit au détriment de la réduction de la plus grande richesse de vos données. Supposons qu’il existe un problème de qualité impliquant sous-réseau 200.1.2.0. Si vous implémenté super-réseaux, vous ne savez où se trouve le sous-réseau dans le bâtiment ou le type de réseau est (par exemple, un laboratoire). Si vous avez défini tous les sous-réseaux d’un bâtiment et télécharger des informations d’emplacement floor, vous ne pourrez pas voir cette distinction.

-   Il est important de s’assurer que l’adresse super-réseaux est correct et qu’il n’est pas intercepter les sous-réseaux.

-   Il est fréquent de rechercher 192.168.0.0 dans les données. Pour de nombreuses organisations, cela indique que l’utilisateur est à domicile. Pour d’autres personnes, il s’agit d’un schéma d’adresse IP pour une succursale. Si votre organisation a des bureaux qui utilisent cette configuration, ne l’inclure dans votre fichier de construction, car il est difficile de faire la distinction entre les réseaux internes et personnel à l’aide de sous-réseaux courantes. Voir la section à propos [des sous-réseaux communs](#common-subnets), plus haut dans ce guide.

> [!IMPORTANT]
> La plage réseau peut être utilisée pour représenter un supernet. Création de toutes les nouvelles données les téléchargements de fichiers qui est vérifié pour toutes les plages qui se chevauchent. Si vous avez précédemment téléchargé un fichier construction, téléchargez le fichier en cours et télécharger à nouveau pour identifier les chevauchements et corriger le problème. Les mappages incorrectes de sous-réseaux aux bâtiments dans les rapports pouvant entraîner un chevauchement des fichiers téléchargés précédemment.

#### <a name="vpn"></a>VPN

Les données de qualité de l’expérience (QoE) qui envoient des clients à Office 365, qui est où sont issues des données CQD — inclut un indicateur VPN. CQD verrez ceci en tant que dimensions VPN première et deuxième VPN. Toutefois, cet indicateur s’appuie sur fournisseurs VPN reporting Windows que la carte du réseau VPN enregistrée est une carte d’accès à distance. Pas de tous les fournisseurs VPN enregistrement correctement les cartes d’accès à distance. Pour cette raison, vous pourrez pas utiliser les filtres de requête VPN intégrés. Il existe deux approches pour les sous-réseaux de réseau privé virtuel dans la création de fichier d’informations :

- Définir un **Nom de réseau** en utilisant le texte « VPN » dans ce champ pour les sous-réseaux de réseau privé virtuel.

  ![Rapport CQD qui définit la création d’un sous-réseau de réseau privé virtuel](media/qerguide-image-vpnnetworkname.png)

  _La figure 12 - VPN à l’aide du nom de réseau_

- Définir le **Nom de la construction** en utilisant le texte « VPN » dans ce champ pour les sous-réseaux de réseau privé virtuel.

  ![Rapport CQD qui définit comment créer une définition de construction qui comprend un sous-réseau de réseau privé virtuel.](media/qerguide-image-vpnbuildingname.png)

  _Figure 13 : VPN à l’aide du nom de la construction_

> [!IMPORTANT]
> Certaines implémentations VPN ne signalent correctement les informations de sous-réseau. Si cela se produit dans votre rapport, qu'il est recommandé que lorsque vous ajoutez un sous-réseau de réseau privé virtuel à la création du fichier, au lieu d’une entrée pour le sous-réseau, ajoutez des entrées pour chaque adresse du sous-réseau de réseau privé virtuel comme un réseau distinct de 32 bits. Chaque ligne peut avoir les mêmes métadonnées de construction. Par exemple, au lieu d’une ligne pour 172.16.18.0/24, vous avez 253 lignes, avec une ligne pour chaque adresse de 172.16.18.1/32 par le biais de 172.16.18.254/32, inclus.


> [!NOTE]
> Les connexions VPN ont été identifiées mal identifier la connexion réseau comme filaire lorsque la connexion internet sous-jacent est sans fil. Lors de la recherche au niveau de qualité sur les connexions VPN, vous ne pouvez pas supposer que le type de connexion a été correctement identifié.

### <a name="uploading-building-information"></a>Chargement des informations de création

Le tableau de bord des rapports de synthèse CQD comprend une page **De téléchargement de données client** , accédée en sélectionnant la balise de lien **De téléchargement de données client** dans le coin supérieur droit (recherchez l’icône représentant un engrenage). Cette page est utilisée pour les administrateurs à télécharger leurs propres informations, telles que le mappage de l’adresse IP et les informations géographiques, mappage de chaque point d’accès sans fil et son adresse MAC et ainsi de suite.

1. Accédez à CQD en ligne en accédant à <https://cqd.lync.com>.

2. Sélectionnez l’icône représentant un engrenage dans le coin supérieur droit et choisissez **De téléchargement de données client** dans la page **Rapports de synthèse** .

   ![Boîte de dialogue qui s’affiche lors du téléchargement de données](media/qerguide-image-tenantdataupload.png)

   _Figure 14 : menu télécharger des données client_

3. Autrement, s’il s’agit de votre première visite CQD, vous devez télécharger les données de création. Vous pouvez sélectionner **Télécharger** pour accéder rapidement à la page **De téléchargement de données client** .

   ![Bannière qui signale un utilisateur de télécharger des données de création](media/qerguide-image-buildingdatauploadbanner.png)

   _Figure 15 : création de bannière de téléchargement de données_

4. Dans la page **De téléchargement de données client** , sélectionnez **Parcourir** pour choisir un fichier de données.

5. Après avoir sélectionné un fichier de données, spécifiez la **date de début** et, le cas échéant, spécifiez une date de fin.

6. Après avoir sélectionné la **date de début**, sélectionnez **Télécharger** pour télécharger le fichier vers CQD. <br><br>Avant que le fichier est téléchargé, il est validé. Si la validation échoue, un message d’erreur s’affiche demandant de corriger le fichier. La figure suivante illustre une erreur ne se produise lorsque le nombre de colonnes dans le fichier de données est incorrect.

   ![Exemple d’une boîte de dialogue qui affiche un message d’erreur lors de l’importation de données de création](media/qerguide-image-buildingdatauploaderror.png)
 
   _Figure 16 : erreur de chargement de données de création_

7. Si aucune erreur ne se produire lors de la validation, le téléchargement du fichier réussit. Vous pouvez voir le fichier de données téléchargées dans la table **Mes téléchargements** , qui affiche la liste complète de tous les fichiers téléchargés pour le client au bas de la page actuels.

> [!NOTE]
> Cela peut prendre jusqu'à quatre heures pour terminer la création du fichier de traitement. <br><br> Si vous avez téléchargé un fichier de construction et pour ajouter les sous-réseaux qui peuvent avoir manquées ou exclus, modifier le fichier d’origine en ajoutant les nouveaux sous-réseaux, supprimez le fichier actuel et téléchargez de nouveau le fichier nouvellement modifié. Il peut y avoir qu’une construction active CQD fichier de données. 


### <a name="updating-a-building-file"></a>Mise à jour d’un fichier de construction

Alors que la collecte de construction et les informations de sous-réseau, les administrateurs chargerez souvent la création du fichier dans plusieurs itérations au fil du temps, l’ajout de nouveaux sous-réseaux et leurs informations de construction telle qu’elle est disponible. Lorsque cela se produit, vous devez télécharger à nouveau votre fichier construction. Ce processus est semblable à la télécharger initiale comme décrit dans la section précédente, à quelques exceptions près comme indiqué dans la section suivante.

> [!Important]
> Construction qu’un seul fichier peut être actif à la fois. Génération de plusieurs fichiers ne sont pas cumulatives.

#### <a name="adding-net-new-subnets"></a>Ajout de nouveaux sous-réseaux net

Il arrive parfois lorsque vous devez ajouter de nouveaux sous-réseaux net à CQD qui étaient initialement partie de votre topologie de réseau. Pour ajouter de nouveaux sous-réseaux net, procédez comme suit dans le portail CQD de téléchargement de données client :

1.  Modifier la création du fichier d’origine et fournir une date de fin qui se produit au moins une journée avant le net nouveaux sous-réseaux ont été acquis.
2.  Téléchargez le fichier d’origine, si vous ne disposez pas d’une copie à jour.
3.  Ajoutez les sous-réseaux nouveau net à la création du fichier d’origine.
4.  Télécharger le fichier modifié récemment construction suivant le même processus que ci-dessus et définir la date de début pour un jour après la fin de la création du fichier précédent.

#### <a name="updating-the-current-building-file"></a>Mise à jour le fichier en cours de création

Si la création du fichier est téléchargé, mais vous devez ajouter les sous-réseaux manquants, procédez comme suit dans le portail CQD de téléchargement de données client :

1.  Téléchargez le fichier d’origine, si vous ne disposez pas d’une copie à jour.
2.  Supprimez le fichier actuel dans CQD.
3.  Ajoutez les sous-réseaux de nouveau dans le fichier d’origine.
4.  Télécharger le fichier de construction. Veillez à définir la date de début au moins huit mois précédent afin que CQD traite les données d’historiques.

### <a name="missing-subnets"></a>Sous-réseaux manquants

Après avoir téléchargé les informations de construction de réseaux gérés, tous les réseaux géré doivent avoir une association de construction. Toutefois, il ne sera toujours le cas ; en règle générale, plusieurs sous-réseaux sont ignorés. Cette section explique comment valider les réseaux manquant.

Accédez à la page **Des rapports détaillés** dans CQD en ligne et accédez au **Rapport de sous-réseau manquant** inclus dans les modèles CQD. Cela présente tous les sous-réseaux avec des flux de 10 ou plus audio qui ne sont pas définis dans les données de création de fichiers et sont marqués comme extérieur. Assurez-vous qu’il n’y a aucun réseaux gérés dans cette liste. S’il manque des sous-réseaux, mettre à jour la construction d’origine du fichier de données et téléchargement de nouveau à CQD.

> [!IMPORTANT]
> Vous devez ajouter votre ID de client comme un filtre de requête pour le **Second ID client** à ce rapport pour filtrer le rapport pour afficher uniquement les données client de votre organisation. Dans le cas contraire, l’état affiche les sous-réseaux fédérés.

> [!NOTE] 
> Veillez à régler le filtre de rapport mois année au mois actuel. Sélectionnez **Modifier**, puis ajustez le filtre de rapport **Mois année** pour enregistrer le nouveau mois par défaut.

![Rapport montrant les sous-réseaux non inclus dans le fichier de données de création de CQD qui illustrent l’utilisation.](media/qerguide-image-missingbuildingreport.png)

_La figure 17 - manquante Création état_

### <a name="building-mapping-tools"></a>Outils de mappage de construction

Nous allons en face, peut être difficile de mappage des sous-réseaux au sein de votre organisation. Grands réseaux globaux sont très complexes, avec les différentes équipes gérer leurs régions respectives, et il ne peut y avoir aucune source unique de la vérité pour la topologie du réseau. Il existe deux outils disponibles pour vous aider à démarrer l’exercice de mappage de construction, décrite dans les sections suivantes.

#### <a name="cqd-tools"></a>Outils CQD

Ces outils sont basés sur PowerShell et peuvent tirer parti des Sites Active Directory (AD) et les Services et les services de Microsoft DHCP pour vous aider à préparer votre fichier de construction.  Ces outils pour les tâches suivantes :

1.  Sites et Services de requête et créer un fichier de construction en fonction des informations contenues dans.
2.  Un serveur DHCP ou serveurs afin d’extraire des informations de sous-réseau et créer automatiquement un fichier de création de requête.
3.  Valider un fichier construction existant, vérification des doublons et les chevauchements.
4.  Trouvez des sous-réseaux non mappés dans CQD.

Pour plus d’informations sur cet outil, voir [ce billet de blog](https://aka.ms/cqdtools).

#### <a name="network-planner"></a>Planificateur de réseau

Le Planificateur de réseau détermine et organise des besoins de votre réseau pour votre déploiement de voix dans le nuage en quelques étapes simples. Grâce à que votre organisation de l’accès réseau détails et utilisation de la voix dans le nuage, vous pouvez obtenir un calcul approximatif de la configuration réseau requise pour votre déploiement de voix dans le nuage, gérer et exporter ces informations pour la création de rapports et afficher des zones pour une analyse plus poussée et suivre les étapes ci-après.

Bien que le Planificateur de réseau n’automatiser le processus de création de mappage entièrement, une fois que les informations de réseau sont entrées dans le Planificateur de réseau, il peut ensuite être exporté vers un fichier construction prêt pour le téléchargement.

Nous vous recommandons de tirer parti du planificateur réseau lors du déploiement des charges de travail multimédia sur votre réseau pour évaluer l’impact global. Pour plus d’informations sur le Planificateur de réseau, visitez le site [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner).


## <a name="diagnostic-alerts"></a>Alertes de Diagnostics

Microsoft surveillance proactive télémétrie CQD pour créer des alertes de diagnostics pour les problèmes connus qui a un impact négatif sur l’expérience utilisateur. Ces alertes sont ensuite automatiquement envoyées à l’administrateur de service via le centre de messages. Le tableau suivant décrit les alertes de diagnostics qui sont indiquées dans le centre de messages, ainsi que des liens vers plus d’informations.

_Tableau 6 - alertes de Diagnostic_

| Alerte                                                                | Plus d’informations             |
|----------------------------------------------------------------------|------------------------------|
| Connus médiocres versions du client sont en cours d’utilisation                   | [Versions du client](#client-versions)              |
| Pilotes audio sont à l’origine de projections d’appel                                 | [Appareils](#devices)                      |
| Restrictions dans le pare-feu sont à l’origine des échecs d’appel du programme d’installation         | [Enquêtes de défaillance du programme d’installation](#setup-failure-investigations) |
| Approfondie des paquets sont à l’origine des échecs d’appel du programme d’installation                | [Enquêtes de défaillance du programme d’installation](#setup-failure-investigations) |
| Appareils de salle de réunion sur les réseaux Wi-Fi sont à l’origine de la qualité des appels médiocres | [Enquêtes de qualité](#quality-investigations)       |
| Le trafic UDP est limité, qui entraîne l’appel de mauvaise qualité         | [TCP](#tcp)                          |
| L’utilisation VPN concerne la qualité des appels                                  | [Enquêtes de qualité](#quality-investigations)       |


### <a name="message-center"></a>Centre de messages

Le centre de message vous avertit des nouvelles mises à jour, des fonctionnalités ou des problèmes. Le centre de messages est disponible dans le centre d’administration Office 365 pour les administrateurs de service. Chaque publication fournit une vue d’ensemble de la mise à jour, la fonctionnalité ou l’émission affecte les utilisateurs et fournit des liens vers des informations plus détaillées.

Pour ouvrir le centre de messages, dans le centre d’administration d’Office 365, accédez à **la santé** > **Centre de messages**, ou sélectionnez la fiche centre de message **d’accueil** du tableau de bord. Le tableau de bord affiche les trois derniers messages qui ont été publiés et les liens à la page Centre de message complet.
 

![La carte de centre de message affiche les trois derniers messages qui ont été validées](media/qerguide-image-messagecentercard.png)

_La figure 18 - fiche centre de Message_

Vous pouvez également utiliser l' [application d’administration d’Office 365](https://go.microsoft.com/fwlink/p/?linkid=627216) sur votre appareil mobile pour afficher le centre de messages, qui est idéal pour garder le contact avec les notifications push. Pour plus d’informations, consultez [cet article](https://support.office.com/article/Message-center-in-Office-365-38FB3333-BFCC-4340-A37B-DEDA509C2093).

## <a name="reliability-investigations"></a>Enquêtes de fiabilité

Pour améliorer la qualité de la première étape consiste à évaluer l’état de la fiabilité dans l’organisation. Étant donné que la fiabilité est vitale pour une expérience utilisateur positive, nous commençons par les deux composants qui mesurent la fiabilité :

1.  **Du programme d’installation des échecs :** L’appel n’a pas pu être établi.

2.  **Drop échecs :** L’appel a été établie et de manière inattendue.

Dans cette section, nous allons couvre les méthodes étudier les deux domaines.

> [!NOTE]
> Pas tous les rapports inclus dans les modèles sont abordées dans ce guide.  Toutefois, les méthodes d’enquête expliqué ci-dessous s’appliquent toujours. Reportez-vous à la description du rapport individuels pour plus d’informations.


### <a name="setup-failures"></a>Échecs d’installation

Hiérarchiser les échecs d’installation appropriées dans ce domaine tout d’abord, car ces défaillances ont un impact négatif sur l’expérience utilisateur.

Commencer votre enquête en évaluant le pourcentage d’échecs de configuration globale pour l’organisation, puis définir la priorité des zones d’enquête en fonction du pourcentage de la plus élevé par bâtiment ou réseau. 

#### <a name="setup-failure-trend-analysis"></a>Analyse des tendances Échec de configuration

Ce rapport affiche la quantité totale de flux, les échecs d’installation de flux et le taux d’échec de flux de données du programme d’installation. Pointez sur l’une des colonnes pour afficher ses valeurs spécifiques, comme le montre la figure suivante. 

![Graphique montrant le pourcentage de flux échecs d’installation](media/qerguide-image-streamsetupfailures.png)

_Échecs de la figure 19 - fiabilité Audio - flux d’installation_

##### <a name="analysis"></a>Analyse

À l’aide de ce rapport, vous pouvez répondre aux questions suivantes et déterminez votre plan d’action suivant :

-   Quel est le pourcentage d’échec total d’appel du programme d’installation pour le mois en cours ?

-   Est le pourcentage d’échec du programme d’installation appel total inférieure ou supérieure à la mesure cible définie ?

-   Est la tendance à l’échec pire supérieures ou égales du mois précédent ?

-   La tendance à l’échec augmente, steady, ou diminue ?

Indépendamment des réponses précédentes, prenez le temps d’étudier la question davantage à l’aide de rapports secondaire Compagnon pour rechercher tout individuelles ou les sous-réseaux qui peuvent nécessiter des mesures correctives. Bien que le taux d’échec global sous la mesure cible, le taux d’échec d’un ou plusieurs bâtiments ou réseaux peut être supérieure à la mesure cible et devez enquête.

#### <a name="setup-failure-investigations"></a>Enquêtes de défaillance du programme d’installation 

Ce rapport de synthèse est utilisé pour détecter et isoler des bâtiments ou des réseaux qui peuvent nécessiter des mesures correctives.

> [!NOTE]
> Veillez à régler le filtre de rapport mois année au mois actuel. Sélectionnez **Modifier**, puis ajustez le filtre de rapport **Mois année** pour enregistrer le nouveau mois par défaut.


![Une liste des raisons pour les échecs d’appel du programme d’installation, organisées par la création, le réseau et sous-réseau par mois](media/qerguide-image-setupfailuresbysubnet.png)

_La figure 20 - échecs de configuration Audio par sous-réseau_

##### <a name="diagnostic-alert"></a>Alerte de diagnostic

Si vous avez reçu une alerte diagnostic « Restrictions dans le pare-feu sont entraînant des échecs des appels du programme d’installation » ou « approfondie des paquets sont entraînant l’échecs des appels du programme d’installation, » vos efforts de correction se concentrer sur les sous-réseaux d’abord identifier. L’alerte a identifié les sous-réseaux qui sont affecter la fiabilité des appels. Vous pouvez utiliser les rapports d’échecs d’installation figurant dans la section de la fiabilité pour vous aider lors de la mise à jour.

##### <a name="remediation"></a>Mise à jour 

Ciblez vos efforts de correction premier de bâtiments ou les sous-réseaux dont le plus grand volume d’échecs. Cela optimiser l’impact sur l’expérience utilisateur et contribuer à réduire les taux d’échec d’installation d’organisation appel rapidement. Le tableau suivant répertorie les deux raisons pour les échecs d’installation tel que signalé par CQD.

_Le tableau 7 – raisons pour le programme d’installation d’échecs d’appel_

| Appelez la raison d’échecs d’installation       | Causes courantes                    |
|----------------------------------|----------------------------------|
| Règle d’Exemption Inspection manquant TR approfondie des paquets | Indique qu’équipement réseau ainsi que le chemin d’accès interdit le chemin d’accès des médias établie en raison des règles d’inspection approfondie des paquets. Il s’agit probablement en raison de règles de pare-feu n’est pas configurés correctement. Dans ce scénario, la négociation TCP a réussi, mais n’a pas de la négociation SSL.      |
| Manque de règle d’Exception de pare-feu IP bloc      | Indique qu’équipement réseau ainsi que le chemin d’accès interdit le chemin d’accès des médias est établie avec le réseau d’Office 365. Cela peut être en raison des règles de proxy ou un pare-feu n’est pas correctement configurés pour autoriser l’accès à des adresses IP et les ports utilisés pour les équipes et Skype pour le trafic d’entreprise. |

Maintenant que vous commencez votre mise à jour, vous pouvez vous concentrer vos efforts sur une construction spécifique ou un sous-réseau. Comme le montre le tableau précédent, ces problèmes sont en raison de configurations de pare-feu ou proxy. Passez en revue les options dans le tableau suivant pour les actions de mise à jour.

_Le tableau 8 - étapes suivantes pour l’appel du programme d’installation de la correction d’erreur_


|      Mise à jour      |                                                                                                                                                                                                                                                                                                                                                                   Aide                                                                                                                                                                                                                                                                                                                                                                   |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configurer l’ou les pare-feu | Travailler avec votre équipe réseau et vérifiez votre configuration ou les pare-feu par rapport à [la liste d’adresses IP de Office 365](https://aka.ms/o365ips).<br><br>Vérifiez que les ports et les [sous-réseaux multimédia](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) sont inclus dans les règles de pare-feu. <br><br>Vérifiez que les ports nécessaires (énumérés ci-dessous) sont ouverts dans le pare-feu. UDP doit être la priorité car TCP est considéré comme un protocole de la restauration automatique pour l’audio, vidéo et partage d’écran vidéo et son utilisation n’affectera la qualité de l’appel. Partage d’application RDP hérité utilise TCP uniquement.<br><ul><li>**TCP :** le port 443</li><li>**UDP :** ports – 3481 3478</li><ul> |
|        Vérifier         |                                                                                                                                                                                                                                                                 Utiliser l' [Outil d’évaluation de réseau Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) pour vérifier la connectivité à partir du bâtiment concerné ou d’un sous-réseau à l’aide de la fonction de vérification de connectivité.                                                                                                                                                                                                                                                                  |

### <a name="drop-failures"></a>Échecs de dépôt

Contrairement aux codes d’erreur du programme d’installation, CDQ n’a aucun code d’échec de dépôt pour indiquer pourquoi dépôt échecs se produisent, qui rend difficile à isoler une cause spécifique. Pour une meilleure triage drop échecs, utilisez une approche déduite. Par corriger toutes les zones d’intérêt pour les médias, mise à jour corrective de clients et pilotes et conduite l’utilisation de périphériques certifiés pour les équipes et Skype pour les entreprises, vous pouvez tirer les échecs de dépôt pour refuser.

#### <a name="drop-failure-trend-analysis"></a>Supprimer l’analyse des tendances Échec

Ce rapport affiche le montant total des flux audio, les échecs de dépôt total et le taux d’échec de dépôt. Pointez sur l’une des colonnes pour afficher ses valeurs, comme le montre la figure suivante. 

![Graphique illustrant le pourcentage de flux de données qui ont été supprimés](media/qerguide-image-droppedstreamrate.png)

_La figure 21 - taux de perte de flux_

##### <a name="analysis"></a>Analyse

À l’aide de ce type de rapport, vous pouvez répondre aux questions suivantes :

-   Quel est le taux d’échec de dépôt actuel ?
-   Est le taux d’échec de déplacement sous la mesure cible définie ?
-   Est la tendance à l’échec pire supérieures ou égales du mois précédent ?
-   La tendance à l’échec augmente, steady, ou diminue ?

Indépendamment des réponses aux questions ci-dessus, prenez le temps d’étudier la question à l’aide de rapports secondaire pour rechercher des réseaux qui peuvent nécessiter des mesures correctives ni de bâtiments. Bien que le taux d’échec global dépôt sous la mesure cible, le taux de défaillance pour un ou plusieurs bâtiments ou réseaux peut être supérieure à la mesure cible et devez enquête.

#### <a name="drop-failure-investigations"></a>DROP enquêtes Échec

Échecs signalés ici indiquent que l’appel a été supprimé de manière inattendue et a provoqué une expérience utilisateur négatif. Contrairement aux rapports tendances, ces rapports fournissent des informations supplémentaires sur des sous-réseaux spécifiques qui nécessitent une étude approfondie.

> [!NOTE]
> Veillez à régler le filtre mois année au mois actuel. Sélectionnez **Modifier**, puis ajuster les **Mois année** pour enregistrer le nouveau mois par défaut.


![Signaler que le nombre de listes et le pourcentage d’échecs de dépôt, organisées par la création, le réseau et sous-réseau par mois](media/qerguide-image-dropfailuresbysubnet.png)

_La figure 22 – échecs de dépôt par sous-réseau_

##### <a name="remediation"></a>Mise à jour

Utiliser les rapports de tableau inclus, vous pouvez isoler problème zones dans le réseau dont le taux est supérieure à la mesure cible vous ont définies. Ciblez vos efforts de correction premier de bâtiments ou les sous-réseaux dont le nombre total de flux de données le plus élevé, pour avoir un impact considérable.

Causes courantes des projections d’appel :

-   Sous-mis en service réseau ou internet sortant
-   Aucun QoS configuré sur les réseaux de contraintes
-   Versions antérieures du client
-   Comportement de l’utilisateur

Une fois que vous détectez des zones de votre problème, vous pouvez utiliser [Analytique appel](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309) à un examen plus approfondi des utilisateurs dans la création des problèmes spécifiques. Appel Analytique contient des données personnelles et peut être utile pour isoler davantage les raisons pour les échecs de dépôt.

Quel que soit l’étape suivante, il est conseillé d’avertir le support technique qu’un problème a été détecté avec bâtiments spécifiques ou les sous-réseaux. De cette manière, ils peuvent rapidement répondre aux appels entrants et trier les utilisateurs plus efficacement. Les utilisateurs avec indicateur peuvent ensuite être renvoyées à l’équipe d’ingénierie examinés.

Le tableau suivant répertorie certaines méthodes courantes pour gérer et résoudre les échecs de dépôt.

_Le tableau 9 - étapes suivantes pour l’appel drop correction_

| Mise à jour                              | Aide                      |
|------------------------------------------|-------------------------------|
| **Réseau à internet**                         | **Congestion**: travailler avec votre équipe réseau pour surveiller la bande passante à bâtiments/sous-réseaux spécifiques pour confirmer qu’il existe des problèmes liés à l’utilisation abusive. Si vous confirmez qu’il existe une surcharge réseau, envisagez l’augmentation de la bande passante à la création ou l’application QoS. Utilisez l’inclus les [rapports de synthèse de flux de mauvaise qualité](#quality-investigations) pour passer en revue les sous-réseaux problème aux problèmes gigue, la latence et la perte de paquets, car ces précède souvent un flux de données déplacée.<br><br>Vous pouvez également utiliser l' [Outil de planification de réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) pour aider à mieux comprendre les besoins en bande passante de votre organisation.<br><br>**QoS**: si l’augmentation de la bande passante n’est pas pratique ou envisageable, envisagez l’implémentation de QoS. Cet outil est très efficace pour gérer le trafic saturé et garantie que les paquets de médias sur le réseau géré sont classés par priorité au-dessus du trafic multimédia non. Ou bien, s’il n’existe aucune clairement que la bande passante est défaillant, prenez en compte ces solutions :<ul><li>[Conseils de QoS des équipes Microsoft](qos-in-teams.md)</li><li>[Skype pour obtenir des instructions Business QoS](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul><br>**Effectuer une évaluation de préparation du réseau**: une évaluation réseau fournit des détails sur l’utilisation de la bande passante attendue, comment faire face à la bande passante et réseau change, réseau pratiques recommandées pour les équipes et Skype pour les entreprises. À l’aide du tableau précédent comme source, vous disposez d’une liste de bâtiments ou les sous-réseaux qui sont une excellente candidats pour une évaluation.<ul><li>[Évaluation de préparation du réseau équipes Microsoft](3-envision-evaluate-my-environment.md#test-the-network)</li><li>[Skype pour l’évaluation de préparation du réseau Business](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Outil d’évaluation de Microsoft Network :** Utilisez cet outil pour un simple test des performances du réseau pour déterminer comment exécuter le réseau pour une équipes ou Skype pour les appels professionnels en ligne. L’outil vous permet d’évaluer les performances d’un sous-réseau et valider la préparation du réseau par rapport à des [exigences](https://aka.ms/performancerequirements)de performances Microsoft.<ul><li>[Télécharger l’outil d’évaluation réseau](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul> |
| **Clients (Skype pour les entreprises en ligne uniquement)** | Certains clients antérieurs ont connu, documentée problèmes avec la fiabilité des supports. Examinez les rapports Analytique appeler à partir de plusieurs utilisateurs concernés, ou créer un rapport de tableau de Version du Client personnalisé dans CQD filtré bâtiments spécifiques ou les sous-réseaux avec mesure de % échec Total appel rejeté. Ces informations vous aideront à comprendre l’existence d’une relation entre projections d’appel dans un bâtiment en particulier et une version spécifique du client.     |
| **Appareils**                                  | Nous recommandons que tous les utilisateurs qui rencontrent appellent projections — ou médiocres appelle en général et sont à l’aide de périphériques intégrés doit être mis en service un [certifié casque ou interphone](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) afin d’éliminer cette source potentielle de mauvaise qualité et la fiabilité. |
| **Comportement de l’utilisateur**                            | Si vous avez déterminé que ni réseau, des périphériques ou des clients sont le problème, envisagez d’engager [Mon Advisor](https://aka.ms/myadvisor) pour obtenir des conseils dans le développement d’une stratégie utilisateur d’adoption apprendre aux utilisateurs comment meilleures joindre et quitter des réunions. Vie équipes et Skype pour utilisateur professionnel produira une meilleure expérience utilisateur pour tous les participants à la réunion. Un utilisateur qui met leur ordinateur portable en mode veille (à la fermeture du capot) sans quitter la réunion est considéré comme une liste d’appel inattendu.   |

## <a name="quality-investigations"></a>Enquêtes de qualité

L’étape suivante pour évaluer l’état de la qualité audio de l’organisation est pour examiner les taux de flux médiocre (qui), TCP et l’utilisation du proxy. Il est important de noter que les données CQD ne fournissent une cause spécifique, mais vous propose des problèmes susceptibles de commencer une conversation collaboration avec les équipes appropriés pour les activités de mise à jour au lieu de cela. 

> [!NOTE]
> Pas tous les rapports inclus dans les modèles sont abordées dans ce guide ; Toutefois, les méthodes d’enquête expliqué ci-dessous seront appliqueront pour ces rapports. Reportez-vous à la description du rapport individuels pour plus d’informations. 

### <a name="quality"></a>Qualité

Les pourcentages qui permettent d’indiquer si l’organisation est objectifs définis métrique pour un domaine donné. Il est important de noter que même si les pourcentages de haut niveau de la cible définie, différents sous-réseaux ou bâtiments ne peut-être pas atteindre les objectifs définis et, par conséquent, nécessitent une étude approfondie. Par exemple, si le pourcentage qui audio général % 2 avril, qui répond à la cible de l’exemple, bâtiments individuels et les sous-réseaux toujours poser une mauvaise expérience, en fonction de la distribution globale des que % 2. 

Pour évaluer le pourcentage de flux médiocres, utilisez les rapports de qualité. Rapports de qualité différents sont fournis pour passer en revue les mesures pour les deux, globale, conférences PSTN appelant, VPN et les salles de réunion. Rapports quotidiennes, hebdomadaires et mensuelles sont fournis pour faciliter ce processus. Rapports hebdomadaires et tous les jours sont limitées au modèle réseaux gérés pour accroître l’efficacité et réduire le bruit. 

#### <a name="quality-trend-analysis"></a>Analyse des tendances de qualité

Rapports sur les tendances affichent des informations sur la qualité au fil du temps et sont utilisés pour aider à identifier et comprendre les tendances de qualité au sein de chaque zone d’intérêt. Comme mentionné ci-dessus, il existe des arborescences de rapport inclus dans les modèles d’analyse de qualité ; conférence, deux, appel PSTN, VPN et les salles de réunion. Pour les besoins de l’analyse de la qualité, le processus d’enquête est la même. Toutefois, il est recommandé que vous commencez à une conférence, car les améliorations de la qualité de conférence également positive affectent tous les autres domaines. 

> [!Note]
> Examen aux deux appels PSTN et les salles de réunion sont similaires aux examen aux conférences. L’objectif est de bâtiments isloate ou les sous-réseaux qui ont la plus mauvaise qualité et d’identifient la cause de la mauvaise qualité.

> [!Important]
> Rapports basés sur un réseau privé virtuel sont filtrés à l’aide de la dimension de la deuxième VPN. Cette dimension requiert que la carte de réseau VPN est correctement enregistré en tant qu’une carte d’accès à distance. Fournisseurs VPN n’utilisent pas cet indicateur fiable et votre mileage varie selon le fournisseur de réseau privé virtuel déployé dans votre organisation. Suivez les instructions indiquées [plus haut dans ce guide](#vpn) pour modifier le réseau VPN signale si nécessaire en utilisant le nom de réseau ou de création.

![Graphique illustrant le pourcentage de flux de données de qualité médiocre](media/qerguide-image-audioqualityconferencing.png)

_La figure 23 – qualité Audio - conférence_

##### <a name="investigation"></a>Enquête

À l’aide de ces rapports, vous pouvez répondre aux questions suivantes :

-   Quel est le total qui pour le mois en cours ?
-   Voici la qui la mesure cible définie ?
-   Est qui pire supérieures ou égales du mois précédent ?
-   La tendance qui augmente, steady, ou diminue ?

Indépendamment des réponses aux questions ci-dessus, prenez le temps d’étudier la question en utilisant les rapports secondaire pour rechercher les bâtiments ou les sous-réseaux qui peuvent nécessiter l’enquête. Bien que le globale qui peut être sous la mesure cible, souvent les régions déterminées pour un ou plusieurs bâtiments ou réseaux au-dessus de la mesure et doivent correction.

#### <a name="quality-investigations"></a>Enquêtes de qualité

La qualité des rapports de synthèse vous donnent plus loin dans ce que contribué pour les flux de données en cours classé comme médiocre et vous aide à isoler les zones de problèmes dans le réseau géré.

Bien que les dimensions utilisées peuvent varier légèrement entre le rapport de chaque rapport inclura mesures de flux total, total flux médiocres, qui et de qualité médiocre pour les raisons. Rapports ont été créés pour chaque zone d’intérêt : salles de conférence, les deux, PSTN appelant, VPN et de la réunion. Le modèle de réseau géré inclut des rapports supplémentaires pour tirer parti des informations d’emplacement téléchargées par le biais de la création du fichier.

> [!NOTE]
> Veillez à régler le filtre mois année au mois actuel. Sélectionnez **Modifier**, puis ajuster les **Mois année** pour enregistrer le nouveau mois par défaut.

> [!Note]
> Sous-réseaux courantes sont difficiles à triage en raison de leur utilisation généralisée. Un rapport distinct qui affiche l’adresse IP publique du client (IP Local réflexive deuxième) a été ajouté au modèle de tous les réseaux pour vous aider à la correction des bureaux qui utilisent des réseaux.


![Flux audio médiocre résumé](media/qerguide-image-poorqualitysummary.png)

_Conférence figure 24 – résumé en créant des flux Audio médiocre - et sous-réseau_

##### <a name="diagnostic-alert"></a>Alerte de diagnostic

Si vous avez reçu un diagnostic alerte « équipements de salle de réunion sur les réseaux Wi-Fi sont à l’origine de la qualité des appels médiocre, » inclure et classer par priorité les périphériques dans vos efforts de correction. L’alerte a identifié les salles de réunion Wi-Fi activement contribuant à la qualité des appels médiocre.

Si vous recevez une alerte de diagnostic « utilisation VPN concerne la qualité des appels, » rechercher une solution pour contourner l’application VPN et autoriser pour vous connecter directement au service de médias tunnel de fractionnement. L’alerte a identifié que VPN affecte la qualité des appels.

##### <a name="remediation"></a>Mise à jour

Ciblez vos efforts de correction de bâtiments ou les sous-réseaux dont le plus grand volume de flux de données, car cela vous aider à améliorer l’expérience utilisateur rapidement et optimiser l’impact. Utilisez la gigue, la perte de paquets et les mesures de temps d’aller-retour (durée aller-retour) de comprendre ce qui contribue à la qualité médiocre (il est possible d’avoir plusieurs problèmes) :

-   **Gigue**: paquets de médias arrivent à différentes vitesses, qui provoque un haut-parleur pour son automatisée.
-   **Perte de paquets**: paquets de médias sont en cours de suppression, qui crée l’effet de mots ou des syllabes manquants.
-   **Durée aller-retour**: paquets de médias sont prend beaucoup de temps pour accéder à leur destination, qui crée un effet talkie-walkie.

Pour aider votre enquête sur les problèmes de qualité, vous pouvez exploiter [Analytique d’appel](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309). Avec l’appel Analytique, vous pouvez examiner une conférence spécifique ou un état d’appel détaillées des utilisateurs. Ce rapport contient les données d’identification personnelle et est utile lorsque vous recherchez la cause d’une défaillance. Une fois que vous connaissez la construction est affectée, il doit être facile de localiser les utilisateurs de cette construction. 

N’oubliez pas d’informer le service d’assistance que ces réseaux rencontrent des problèmes de qualité, afin qu’ils puissent rapidement triage et répondre aux appels entrants.

_Tableau 10 - courantes collaborateurs à haute qui_

| Mise à jour                              | Aide                         |
|------------------------------------------|----------------------------------|
| **Réseaux**                                 | **Congestion**: un utilisation excessive ou configurées sous réseau peut entraîner des problèmes avec la qualité des médias. Travail avec l’équipe réseau pour déterminer si les connexions réseau à partir de l’utilisateur à la sortie internet point a suffisamment de bande passante pour prendre en charge multimédia. Le [Planificateur de réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) peut vous aider à mieux comprendre les besoins en bande passante de votre organisation.<br><br>**Effectuer une évaluation de préparation du réseau**: une évaluation réseau fournit des détails sur l’utilisation de la bande passante attendue, comment faire face à la bande passante et réseau change, réseau pratiques recommandées pour les équipes et Skype pour les entreprises. À l’aide du tableau précédent comme source, vous disposez d’une liste de bâtiments ou les sous-réseaux qui sont une excellente candidats pour une évaluation.<ul><li>[Évaluation de préparation du réseau équipes Microsoft](3-envision-evaluate-my-environment.md#test-the-network)</li><li>[Skype pour l’évaluation de préparation du réseau Business](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Outil d’évaluation de Microsoft Network :** Utilisez cet outil pour un simple test des performances du réseau pour déterminer comment exécuter le réseau pour une équipes ou Skype pour les appels professionnels en ligne. L’outil vous permet d’évaluer les performances d’un sous-réseau et valider la préparation du réseau par rapport à des [exigences](https://aka.ms/performancerequirements)de performances Microsoft.<ul><li>[Télécharger l’outil d’évaluation réseau](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul><br> |
| **Qualité de service (QoS)**  | QoS est un outil éprouvé pour aider à définir la priorité des paquets sur un réseau saturé pour s’assurer qu’ils arrivent à destination intacte et sur le temps. Envisagez d’implémenter la qualité de service au sein de votre organisation afin d’optimiser la qualité de l’expérience utilisateur dans lequel la bande passante est limitée. QoS vous aideront à résoudre les problèmes généralement associés avec un niveau élevé de perte de paquets, et, dans une moindre mesure : temps de gigue et aller-retour.<ul><li>[Conseils de QoS des équipes Microsoft](qos-in-teams.md)</li><li>[Skype pour obtenir des instructions Business QoS](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul> |
| **Wi-Fi**               | Wi-Fi peut avoir un impact significatif sur la qualité des appels. Déploiements Wi-Fi ne généralement prennent en considération la configuration réseau requise pour les services VoIP et sont souvent une source de qualité médiocre. Pour plus d’informations sur l’optimisation de votre infrastructure Wi-Fi, consultez [cet article sur la planification de Wi-Fi](/skypeforbusiness/certification/plan-wifi).<br><br>**Pilote sans fil**: s’assurer que les pilotes sans fil sont à jour. Cela permettra d’atténuer les expérience utilisateur médiocre lié à un pilote obsolète. Bon nombre d’organisations n’incluez pas pilotes sans fil dans leur cycle de correctif et ces pilotes peuvent atteindre des années. De nombreux problèmes sans fil sont résolus en vérifiant que les pilotes sans fil sont à jour.<br><br>**WMM**: Extensions de sans fil multimédia (WMM), également appelé Wi-Fi multimédia, fournit les fonctionnalités de QoS base aux réseaux sans fil. Les réseaux sans fil modernes doivent prendre en charge de nombreux périphériques. Ces périphériques en concurrence pour la bande passante et peuvent entraîner des problèmes de qualité des services VoIP, où la vitesse et la latence sont essentielles. Consultez votre fournisseur sans fil pour caractéristiques et implémentez WMM sur votre réseau sans fil pour classer par priorité Skype pour professionnels et les équipes de support.<br><br>**Densité du point d’accès**: points d’accès peuvent être trop éloignés ou non dans un emplacement idéal. Pour réduire l’interférence potentielle, placez les points d’accès supplémentaires dans les salles de conférence et dans les emplacements qui ne sont pas coupés par les murs ou d’autres objets où le signal Wi-Fi est faible.<br><br>**2,4 GHz et 5 GHz**: 5 GHz fournit moins interférences d’arrière-plan et le plus rapidement et priorité lors du déploiement VoIP en Wi-Fi. Toutefois, 5 GHz n’est pas aussi forte que 2,4 GHz et ne traversent les murs aussi facilement. Passez en revue votre mise en page de construction pour déterminer quelle fréquence dépendent de la meilleure connexion. |
|**Périphérique de réseau** | Organisations de grande taille peuvent avoir des centaines de périphériques répartis sur le réseau. Travailler avec votre équipe réseau afin de vous assurer que les périphériques réseau à partir de l’utilisateur à internet sont gérées et à jour. |
| **VPN**  | Appareils VPN ne sont pas généralement conçus pour gérer les charges de travail de médias en temps réel. Certaines configurations VPN interdisent l’utilisation de UDP (qui est le protocole par défaut pour les médias), ils s’appuient sur TCP uniquement. Envisagez d’implémenter une [solution de fractionnement-tunnel VPN](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) pour réduire VPN en tant que source de qualité médiocre. |
| **Clients** <br>(Skype pour les entreprises en ligne uniquement) | Clients antérieurs ont été identifiés pour provoquer des problèmes de support. Assurez-vous que les clients corrigés dans les six mois de version. Utilisez [MyAdvisor](https://aka.ms/myadvisor) pour obtenir des instructions sur le développement d’une stratégie de préparation des clients et deploy [Click-to-Run](https://docs.microsoft.com/DeployOffice/deployment-guide-for-office-365-proplus). |
| **Appareils** | L’utilisation de [optimisé périphériques](https://partnersolutions.skypeforbusiness.com/solutionscatalog) peut aider à améliorer sensiblement l’expérience utilisateur. Tout ce qui est égal, périphériques optimisés sont conçus pour optimiser l’expérience utilisateur avec des équipes et Skype pour les entreprises et de qualité supérieure. Utilisez [MyAdvisor](https://aka.ms/myadvisor) pour obtenir des instructions sur le développement d’une stratégie de disponibilité du périphérique. |
| **Pilotes** | Mise à jour corrective réseau (Ethernet et Wi-Fi), audio, vidéo et pilotes USB doit faire partie de votre stratégie globale de gestion des correctifs. Nombre de problèmes de qualité sont résolus en mettant à jour les pilotes. |
| **Salles de réunion Wi-Fi** | Il est fortement recommandé que les réunions équipements de salle être connecté au réseau à l’aide d’au moins une connexion de Ethernet 1 Gbit/s. Périphériques de la salle de réunion incluent généralement plusieurs flux audio et vidéo, ainsi que de telles que le partage d’écran, contenu de la réunion et supérieur réseau exige d’autres équipes ou de Skype pour systèmes d’extrémité Business. Salles de réunion sont, par définition, périphériques fixes où Wi-Fi offre un avantage uniquement pendant l’installation.<br><br>Salles de réunion doivent être traités avec précaution et attention pour s’assurer que l’expérience de l’utilisation de ces périphériques est de réunion ou attentes. Problèmes de qualité avec les salles de réunion sont généralement sur le point d’être modifiée rapidement, car ils sont souvent utilisés par le personnel de haut niveau.<br><br>Tout ce qui est égal (à l’exception commodité), performances Wi-Fi est souvent inférieur à une connexion câblée. Avec l’augmentation de stratégies « apportez votre propre appareil » et la prolifération des ordinateurs portables, les points d’accès Wi-Fi sont souvent trop utilisées. Médias en temps réel ne peut pas être prioritaires sur les réseaux Wi-Fi, ce qui peuvent entraîner des problèmes de qualité pendant les heures d’utilisation maximale. Cette utilisation intensive peut coïncider avec une réunion où il existe une dizaine personnes de présence, chacun avec leur propre ordinateur portable et un smartphone, tous connecté au même point d’accès Wi-Fi comme réunion périphérique.<br><br>Wi-Fi seulement doit être considéré comme solution temporaire, pour une installation mobile ou Wi-Fi a été correctement configurée pour prendre en charge multimédia professionnelles, basé sur le temps réel. |


### <a name="tcp"></a>TCP

TCP est considéré comme un pas le transport principal souhaité pour les médias en temps réel et la restauration automatique. Il s’agit d’un transport de la restauration automatique est en raison de la nature dynamique du protocole TCP. Par exemple, si un appel est effectué sur un réseau latent et paquets de médias sont retardées, puis les paquets d’il y a quelques secondes, qui ne sont plus utile — en concurrence pour la bande passante atteindre le récepteur, qui permet de rendre un pire situation incorrecte. Cela rend l’agrafage de réparation audio et audio étirement, entraînant des artefacts sonores, souvent sous la forme de gigue.

Les rapports de cette section n’apporte une différence entre une bonne et une mauvaise flux. Étant donné que UDP est par défaut, les rapports recherchez l’utilisation de TCP pour l’écran audio, vidéo et vidéo, partage (VBSS). Taux faible de flux sont fournis pour aider à comparer la qualité et la qualité TCP UDP afin que vous puissiez concentrer vos efforts où l’impact est le plus grand. L’utilisation TCP est principalement dû à des règles de pare-feu incomplètes. Pour plus d’informations sur les règles de pare-feu pour les équipes et Skype pour Business Online, voir [Office 365 URL et plages d’adresses IP](https://aka.ms/o365ips).

> [!Important]
> Avoir une [création valide du fichier](#building-mapping) téléchargé est vivement recommandé afin que vous pouvez rapidement distinguer à l’intérieur des flux de données externes lorsque vous examinez l’utilisation TCP.

> [!Note]
> Audio, vidéo et VBSS préfèrent UDP comme transport principal. La charge de travail hérité partage d’Application RDP utilise TCP.

#### <a name="tcp-usage"></a>Utilisation TCP

Rapports TCP indique l’utilisation TCP globale sur les sept derniers mois. Tous les autres rapports dans cette section seront concentre sur la limitation de bâtiments spécifiques et les sous-réseaux où TCP est généralement utilisée. Rapports distincts sont disponibles pour la conférence et deux flux.

![Graphique avec le pourcentage de flux audio qui utilisent le protocole TCP](media/qerguide-image-audiostreamswithtcp.png)
_Figure 25 – flux Audio avec l’utilisation de TCP_


##### <a name="investigation"></a>Enquête

À l’aide de ce rapport, vous pouvez répondre aux questions suivantes :

-   Quel est le volume total de flux de données TCP pour le mois en cours ?
-   Est-il pire supérieures ou égales du mois précédent ?
-   Les tendances d’utilisation TCP augmente, steady, ou diminue ?
-   Équivaut à la PSR TCP mon globale qui ?

Si vous constatez que les tendances d’utilisation TCP augmente ou au-dessus d’utilisation mensuelle normale, prenez le temps d’étudier la question en utilisant les rapports secondaire pour rechercher des bâtiments ou des réseaux qui peuvent nécessiter des mesures correctives. Dans l’idéal, vous souhaitez sessions audio basés sur TCP aussi peu que possible sur le réseau géré.

#### <a name="tcp-vs-udp"></a>TCP et UDP

Ce rapport identifie le volume du protocole TCP par rapport à l’utilisation UDP création de rapports sur le dernier mois pour écran audio, vidéo et vidéo, partage (VBSS). 

![Rapport illustrant le volume de flux de données qui utilisent le protocole TCP et UDP](media/qerguide-image-tcpvsudp.png)

_La figure 26 – TCP et UDP - conférence_

##### <a name="analysis"></a>Analyse

Bien que vous souhaitez que l’utilisation TCP pour être aussi faible que possible, vous pouvez voir un bit d’utilisation TCP dans un déploiement intègre dans le cas contraire. TCP en lui-même ne contribue à un appel médiocre, afin de taux de flux de données sont fournis pour aider à déterminer si l’utilisation TCP est un collaborateur de qualité médiocre. 

#### <a name="tcp-investigations"></a>Enquêtes TCP

Dans les modèles fournis CQD, accédez à flux TCP par sous-réseau et création de rapports à l’aide du modèle de réseaux gérés ou de tous les réseaux. Pour les besoins de recherches sur l’utilisation TCP, le processus est la même, afin que nous nous concentrerons ici la discussion sur la conférence.

> [!IMPORTANT]
> Avoir une valide de [création du fichier](#building-mapping) téléchargé est recommandée afin que vous pouvez rapidement distinguer à l’intérieur des flux de données externes lorsque vous examinez l’utilisation TCP. 

> [!NOTE]
> Veillez à régler le filtre mois année au mois actuel. Sélectionnez **Modifier**, puis ajuster les **Mois année** pour enregistrer le nouveau mois par défaut.                                  |

![Utilisation TCP en créant et en sous-réseau](media/qerguide-image-tcpstreams.png)

_La figure 27 – flux TCP en créant - et sous-réseau conférence_

##### <a name="diagnostic-alert"></a>Alerte de diagnostic

Si vous avez reçu une alerte diagnostics « le trafic UDP est limité, qui entraîne l’appel de mauvaise qualité, » concentrer vos efforts de correction TCP sur ces sous-réseaux tout d’abord. L’alerte a identifié les sous-réseaux où l’utilisation de TCP affecte la qualité des appels.

##### <a name="remediation"></a>Mise à jour

Ce rapport identifie bâtiments spécifiques et les sous-réseaux qui travaillent pour le volume de l’utilisation TCP. Un rapport supplémentaire est également inclus pour identifier l’adresse IP relais Microsoft qui a été utilisé dans l’appel pour isoler les règles de pare-feu manquant. Ciblez vos efforts de correction sur ces bâtiments qui ont le plus grand volume de flux de données TCP afin d’optimiser l’impact.

La cause la plus courante de l’utilisation TCP n’a pas de règles d’exception de pare-feu ou proxy. Nous parler des proxys dans la section suivante, donc pour l’instant concentrer sur les pare-feu. À l’aide de la création ou le sous-réseau fourni, vous pouvez déterminer le pare-feu doit être mis à jour.


_Le tableau 11 - instructions de correction pour les flux TCP en créant et en sous-réseau_

| Mise à jour        | Aide     |
|--------------------|--------------------------------------|
| Configurer le pare-feu | Vérifiez que les [adresses et les ports d’Office 365 IP](https://aka.ms/o365ips) sont exclus à partir de votre pare-feu. Pour les problèmes TCP relatifs aux médias, concentrer initiale sur les éléments suivants :<ul><li>Vérifiez que le client multimédia sous-réseaux 13.107.64.0/18 et 52.112.0.0/14 se trouvent dans vos règles de pare-feu.</li><li>Les ports UDP 3478 – 3481 sont les ports multimédias obligatoire et doivent être ouvert, sinon le client est restauré sur le port TCP 443.</li></ul> |
| Vérifier             | Utiliser l' [Outil d’évaluation de réseau Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) pour vérifier les problèmes de connectivité à des ports et adresses Office 365 IP spécifiques à partir de la construction concernée ou le sous-réseau.    |

### <a name="http-proxy"></a>Proxy HTTP

Serveurs proxy HTTP ne sont pas le chemin d’accès par défaut pour l’établissement des sessions multimédias, d’une multitude de raisons. Nombreuses contiennent des fonctionnalités d’inspection approfondie des paquets peuvent empêcher les connexions au service en cours d’exécution et présenter les interruptions de service. En outre, presque tous les proxys force TCP et ne pas autoriser UDP, qui est recommandée pour une qualité audio optimale.

Nous recommandons de toujours configurer le client se connecte directement aux équipes et Skype pour les services. Ceci est particulièrement important pour le trafic multimédia.


> [!IMPORTANT]
> Avoir une valide de [Création de fichier](#building-mapping) téléchargé facilite la distinguer correctement à l’intérieur des flux audio externes lors de l’analyse de l’utilisation du proxy. 


#### <a name="http-proxy-usage"></a>Utilisation du proxy HTTP

L’état de flux de proxy HTTP dans cette section du modèle est très similaire les rapports TCP. Il ne s’affiche si les appels sont médiocres ou bon, mais si l’appel est connecté via HTTP.

![Rapport de flux audio qui utilisent le protocole HTTP](media/qerguide-image-audiostreamswithhttp.png)

_La figure 28 – flux Audio avec l’utilisation du Proxy HTTP_

##### <a name="analysis"></a>Analyse

Vous souhaitez afficher sous forme de flux de média HTTP peu que possible. Si vous avez flux parcourir votre proxy, contactez votre équipe de mise en réseau pour vous assurer que les exclusions appropriées sont en place afin que les clients sont directement de routage pour les équipes ou Skype pour les sous-réseaux media Business en ligne.

Si vous n'avez qu’un seul proxy internet dans votre organisation, vérifiez le bon [Office 365 URL et les exclusions de plage d’adresses IP](https://aka.ms/o365ips). Si plusieurs proxy internet est configuré dans votre organisation, utilisez le protocole HTTP sous-fonctionnalités signaler pour isoler le bâtiment ou sous-réseau est affecté.

Pour les organisations qui ne peuvent pas contourner le serveur proxy, vérifiez que le Skype pour client d’entreprise est configurée pour se connecter correctement lorsqu’il est situé derrière un serveur proxy, comme indiqué dans l’article [Skype pour les entreprises doit utiliser serveur proxy pour se connecter au lieu d’essayer direct connexion](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin). 


#### <a name="http-proxy-investigations"></a>Enquêtes de proxy HTTP

Ce rapport identifie bâtiments spécifiques et les sous-réseaux à l’utilisation HTTP.

> [!IMPORTANT]
> Avoir une valide de [Création de fichier](#building-mapping) téléchargé facilite la distinguer correctement à l’intérieur des flux audio externes lors de l’analyse de l’utilisation du proxy.

> [!NOTE]
> Veillez à régler le filtre mois année au mois actuel. Sélectionnez **Modifier**, puis ajuster les **Mois année** pour enregistrer le nouveau mois par défaut.

![Rapport d’utilisation de Proxy HTTP en créant et sous-réseau](media/qerguide-image-httpproxyusage.png)

_Figure 29 – utilisation de Proxy HTTP en créant et sous-réseau_

##### <a name="remediation"></a>Mise à jour

Nous [vous recommandons de](proxy-servers-for-skype-for-business-online.md) toujours ignorer les proxys de Skype pour les professionnels et les équipes, notamment le trafic multimédia. Proxys ne sécuriser Skype pour les entreprises, car le trafic est déjà chiffré. Des problèmes de performances peuvent s'introduire dans l'environnement par le biais de la latence et la perte de paquets. Problèmes tels que ceux-ci entraînera une expérience négative audio, vidéo et partage d’écran, où les flux de données en temps réel est essentielles.

La cause la plus courante de l’utilisation HTTP n’a pas de règles d’exception de proxy. Contournement de média à l’aide de la création ou le sous-réseau fourni, vous pouvez déterminer rapidement le proxy doit être configuré pour le média.

Vérifiez que le requis [Office 365 complets](https://aka.ms/o365ips) sont autorisés dans votre serveur proxy.

Pour plus d’informations sur l’utilisation des proxys avec Skype pour Business en ligne et les équipes, consultez [cet article](proxy-servers-for-skype-for-business-online.md).

## <a name="endpoint-investigations"></a>Enquêtes de point de terminaison

Cette section se concentre sur les tâches de création de rapports sur les versions du client et l’utilisation de périphériques certifiés. Les rapports sont disponibles pour le plan d’utilisation pour les versions du client, type de client, périphériques de capture et pilotes (microphone), les périphériques de capture vidéo et versions de fournisseur et le pilote Wi-Fi.

> [!NOTE]
> Pas tous les rapports inclus dans les modèles sont abordées dans ce guide ; Toutefois, les méthodes d’enquête expliqué ci-dessous s’appliquent toujours. Reportez-vous à la description du rapport individuels pour plus d’informations.

### <a name="client-versions"></a>Versions du client

Les rapports de cet espace se concentrer sur l’identification Skype pour les versions de client d’entreprise en cours d’utilisation et leur volume relative dans l’environnement.

> [!IMPORTANT]
> Actuellement, les équipes clients sont distribués et mis à jour automatiquement via le réseau de livraison de contenu Azure et seront conservés à jour par le service. Préparation des clients et activités investigation ne sont pas applicables aux équipes.

> [!Important]
> Sauf si vous excluez les données de participants fédérées, ces rapports inclura télémétrie client à partir de points de terminaison fédérés. Pour exclure les points de terminaison fédérées, vous devez ajouter un [filtre de requête](#query-filters) pour deuxième identifiant client de votre organisation [d’ID de client](#tenant-id). Autrement, vous pouvez utiliser un [filtre d’URL](#url-filter) à exclure télémétrie participant fédéré.

> [!NOTE]
> Veillez à régler le filtre mois année au mois actuel. Sélectionnez **Modifier**, puis ajuster les **Mois année** pour enregistrer le nouveau mois par défaut.

![Rapport de clients et périphériques](media/qerguide-image-clientversionreport.png)

_La figure 30 - état de la version de Client_

#### <a name="diagnostic-alert"></a>Alerte de diagnostic

Si vous avez reçu un diagnostic l’alerte « connus médiocres versions du client sont en cours d’utilisation », vous concentrer tout d’abord la mise à jour des clients. L’alerte a identifié que ces clients sont affecter négativement la qualité des appels. Vous pouvez utiliser la & Client rapport d’appareils (illustré ci-dessus) pour vous assurer que les clients qui ont des problèmes connus sont ne sont plus mis à jour.

#### <a name="remediation"></a>Mise à jour

Un rôle essentiel de conduite expériences utilisateur de qualité est de vous assurer que gérées clients exécutant des versions à jour de Skype pour les entreprises, en plus d’assurer la prise en charge audio, la vidéo, le réseau et les pilotes USB sont à jour. Cela offre plusieurs avantages, parmi lesquels : 

-   Il est plus facile de gérer plusieurs versions et le nombre de versions.
-   Il fournit un niveau de cohérence de l’expérience.
-   Il est plus facile de résoudre les problèmes liés à la qualité des appels et de la convivialité.
-   Microsoft met continuellement optimisations et améliorations générales sur le produit. S’assurer que les utilisateurs reçoivent ces mises à jour permet de réduire les risques de rencontrez un problème qui a déjà été résolu.

Limitation de votre déploiement sur les versions du client qui sont moins de six mois pour améliorer l’expérience utilisateur globale et faciliter la gestion en réduisant le nombre de versions qui doivent être pris en charge.

Si vous utilisez uniquement Office Click-to-Run, vous serez automatiquement pendant la période de six mois. Aucune action supplémentaire n’est requise.

Si vous avez un mélange de Click-to-Run et packages installer (MSI), vous pouvez utiliser le rapport pour vérifier que les clients MSI sont mis à jour régulièrement. Si vous remarquez retard de clients, travailler avec l’équipe chargée de la gestion des mises à jour Office et vous assurer qu’ils sont l’approbation et déploiement de correctifs client régulièrement.

Il est également important à prendre en compte et vérifiez que le réseau, vidéo, USB et pilotes audio en cours corrigés ainsi. Il peut être facilement ignore ces pilotes et pas les inclure dans votre stratégie de gestion des correctifs.

Vous pouvez trouver les numéros de version de Skype pour les entreprises via les liens ci-dessous :

-   [Publication des informations mises à jour pour Office ProPlus](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)
-   [Historique de mise à jour pour Office 365 ProPlus](https://docs.microsoft.com/officeupdates/update-history-office365-proplus-by-date)
-   [Téléchargements et mises à jour de Skype Entreprise](/SkypeForBusiness/software-updates)

### <a name="devices"></a>Appareils

Faire utiliser le rapport de périphérique microphone, nous devons comprendre le concept de la moyenne d’opinion (MOS). MOS est la mesure standard or pour évaluer la qualité audio. Il est représenté sous la forme d’une note de nombre entier de 0 à 5.

La base de toutes les mesures de qualité de voix est la façon dont une personne perçoit la qualité de voix. Car il est affecté par la perception humaine, il est fondamentalement subjectivement. Il existe plusieurs méthodologies de test subjectivement. La plupart des mesures de qualité de voix sont basées sur une échelle d’évaluation (blocage) catégorisation absolue.

Dans un test subjectivement blocage, un nombre important de statistiques de personnes taux leur qualité de l’expérience sur une échelle de 1 (mauvais) à 5 (excellent). La moyenne des scores est la note MOS de qualité. La note MOS qualité qui en résulte dépend de la plage des expériences qui ont été exposés pour le groupe et le type de l’expérience d’évaluation.

Car il est difficile d’effectuer des tests subjectives de qualité de voix pour un système de communication live, Microsoft Teams et Skype pour les entreprises génèrent valeurs MOS à l’aide des algorithmes pour prévoir objective les résultats d’un test subjectivement.

Le jeu disponible de MOS et mesures associé fournit une vue de la qualité de l’expérience remis aux utilisateurs par un périphérique audio. 

En fournissant aux utilisateurs des périphériques certifiés pour les équipes et Skype pour les entreprises, vous réduisez la probabilité de rencontrer des expériences négatives en raison de l’appareil lui-même (qui est plus probable, par exemple, avec les microphones et les haut-parleurs intégrés). Pour plus d’informations, voir ces articles sur le [programme de certification](/SkypeForBusiness/certification/overview) et le [catalogue des solutions partenaires](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs).

Les rapports de périphériques sont utilisés pour évaluer l’utilisation du périphérique en volume et MOS score (audio uniquement) et se trouve dans les modèles d’accompagnement sous Clients & périphériques. 

> [!IMPORTANT]
> Sauf si vous excluez les données de participants fédérées, ces rapports inclura télémétrie client à partir de points de terminaison fédérés. Pour exclure les points de terminaison fédérés, vous devez ajouter un filtre de requête pour **Second ID client** de votre organisation [d’ID de client](#tenant-id). Autrement, vous pouvez utiliser un [filtre d’URL](#url-filter) à exclure télémétrie participant fédéré.

> [!NOTE] 
> Veillez à régler le filtre mois année au mois actuel. Sélectionnez **Modifier**, puis ajuster les **Mois année** pour enregistrer le nouveau mois par défaut.

> [!Note]
> Vous pouvez remarquer lorsque ce rapport que vous voyez le même périphérique signalé plusieurs fois. Il s’agit en raison de la façon dont le périphérique est indiqué dans CQD. Différences dans le matériel et les paramètres régionaux du système d’exploitation provoquer des différences dans la manière dont les données du périphérique sont signalées.

![Rapport de périphériques (Microphone)](media/qerguide-image-devicesmicrophone.png)

_Figure 31 - signalent des périphériques (Microphone)_

##### <a name="diagnostic-alert"></a>Alerte de diagnostic

Si vous avez reçu une alerte de diagnostic « pilotes Audio sont à l’origine de projections d’appel, » concentré sur corriger ces pilotes tout d’abord. L’alerte a identifié que mauvais pilotes connus sont à l’origine des appels pour supprimer et sont affecter la fiabilité des appels. Vous pouvez utiliser le Microphone-rapport sur les pilotes (illustré ci-dessus), qui se trouve dans la section périphériques de & Client, pour faciliter le processus.

##### <a name="remediation"></a>Mise à jour

En règle générale, vous devez détecter et supprimer progressivement les périphériques non certifiés et les remplacer par les périphériques certifiés. Certaines considérations lorsque vous examinez les rapports d’appareil sont les suivantes :

-   Les périphériques sont-ils utilisés certifiés pour les équipes et Skype pour les entreprises ? 
-   Vous pouvez identifier les utilisateurs d’un périphérique spécifique via [Analytique d’appel](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309). Vérifiez pour vous assurer qu’ils ont les derniers pilotes de périphériques et que leur appareil n’est pas connecté via un concentrateur USB ou une station d’accueil. 
-   Combien de différentes versions des pilotes différents sont en cours d’utilisation ? Ils en cours corrigés régulièrement ? S’assurer que les paramètres audio, vidéo et pilotes Wi-Fi sont en cours mis à jour régulièrement aideront éliminer ces en tant que source de problèmes de qualité et améliorer l’expérience utilisateur plus prévisible et cohérente.

##### <a name="audio"></a>Audio

L’étape suivante consiste à déterminer l’utilisation globale des [périphériques audio certifiés](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). Nous vous recommandons qu’au moins 80 % de tous les flux audio d’un périphérique audio certifié. Cette opération s’effectue mieux en exportant le rapport de périphériques de microphone vers Excel pour calculer l’utilisation de périphériques certifiés ou approuvés. Les organisations conservent généralement une liste de tous les périphériques approuvées, filtrage et tri des données doivent être simples.

##### <a name="video"></a>Vidéo

Les pilotes vidéo sont importants de garder également mis à jour. S’assurer que les cartes vidéo sont en cours régulièrement corrigés aident à exclure les pilotes vidéo en tant que source de mauvaise qualité des flux vidéo. À l’aide de [périphériques vidéo certifiés](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) afin de garantir une expérience utilisateur transparente et de haute qualité. Les périphériques vidéo qui prennent en charge le codage H.264 native préférés, afin de réduire l’utilisation du processeur au cours de la visioconférence.

##### <a name="wi-fi"></a>Wi-Fi

Pilotes Wi-Fi doivent être appliqué sur une cadence régulière ainsi également et doivent être inclus dans votre stratégie de gestion des correctifs. Nombre de problèmes de qualité peuvent être corrigés en conservant les pilotes Wi-Fi à jour. Pour plus d’informations sur l’optimisation de votre infrastructure Wi-Fi, consultez [cet article sur la planification de Wi-Fi](/skypeforbusiness/certification/networking-wifi).

## <a name="appendix"></a>Annexe 

### <a name="office-365-network-connectivity-principles"></a>Principes de connectivité réseau Office 365

Avant de commencer la planification de votre réseau Office 365 la connectivité réseau, il est important de comprendre les principes de connectivité de gérer en toute sécurité le trafic d’Office 365 et d’obtenir les meilleures performances possibles. L’article suivant vous aideront à comprendre les plus récents conseils pour éliminer en toute sécurité la connectivité réseau Office 365 :

[Principes de connectivité réseau Office 365](https://aka.ms/pnc)

### <a name="planning-for-wi-fi"></a>Planification pour Wi-Fi

L’approche de Microsoft pour agilité dans les réseaux sans fil et la qualité du lecteur est fourni en trois parties : planification de bout en bout, meilleures pratiques en matière de déploiement et les opérations et maintenance proactive. Cette présentation de la solution vous guide tout au long de ce processus pour garantir un Skype sans fil d’entreprise pour une expérience :

[Assurer une Skype sans fil de classe de contenu d’entreprise pour une expérience](https://www.microsoft.com/download/details.aspx?id=47257)

### <a name="lync-networking-guide"></a>Guide de mise en réseau de Lync

Pour plus d’informations sur les équipes et Skype pour des concepts de réseau d’entreprise et les raisons justifiant leur importance à la qualité, le [Guide de mise en réseau de Lync Server 2013](https://blogs.technet.microsoft.com/nexthop/2013/06/03/lync-server-2013-networking-guide-network-planning-monitoring-and-troubleshooting-with-microsoft-lync-server/) est toujours applicables.

### <a name="network-performance-requirements"></a>Exigences de performances réseau

La qualité des médias en temps réel (audio, vidéo et partage d’application) sur IP est considérablement affectée par la qualité de la connectivité réseau de bout en bout. Des équipes ou des Skype pour la qualité des médias optimales, votre réseau doit respecter les mesures de performances réseau suivantes.

_Le tableau 12 - des exigences de performances réseau_

| Mesure                            | Client Microsoft Edge           | Côté client pour Microsoft Edge    |
|-----------------------------------|------------------------------------|------------------------------------|
| Latence (unidirectionnelle)                 | \<50 ms                            | \<30 ms                            |
| Latence (temps d’aller-retour ou durée aller-retour) | \<100 ms                           | \<60 ms                            |
| Perte de paquets en rafale                 | \<10 % au cours de l’intervalle de 200-ms   | \<1 % au cours de l’intervalle de 200-ms    |
| Perte de paquets                       | \<1 % au cours de l’intervalle de 15-s    | \<0,1 % au cours de l’intervalle de 15-s  |
| Gigue arrivée entre des batteries de paquets       | \<30 ms pendant l’intervalle de 15-s | \<15 ms pendant l’intervalle de 15-s |
| Réorganisation des paquets                    | \<paquets d’ordre 0,05 %       | \<paquets d’ordre 0,01 %      |

Pour plus d’informations, consultez [cet article sur média qualité et les performances réseau](https://aka.ms/performancerequirements) pour les équipes et Skype pour Business Online.

### <a name="other-resources"></a>Autres ressources

#### <a name="building-data-file"></a>Fichier de données de création

-   [Activation et à l’aide de tableau de bord qualité d’appel pour Microsoft Teams et Skype pour Business Online](turning-on-and-using-call-quality-dashboard.md)

#### <a name="cqd-training"></a>Formation CQD

-   <https://aka.ms/sof-cqd>

-   Atelier et guide de [mise en route avec CQD](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Configuring%20Call%20Quality%20Dashboard%20to%20monitor%20your%20Skype%20for%20Business%20Online%20Environment)

-   [Dimensions et mesures disponibles dans le tableau de bord de qualité des appels](https://aka.ms/cqd-dm)

### <a name="call-analytics-training"></a>Appel de formation Analytique

-   [Présentation Analytique d’appel](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)

-   [Configurer l’analyse des appels](set-up-call-analytics.md)

-   [En quoi l'analyse des appels et le tableau de bord de qualité des appels sont-ils différents ?](difference-between-call-analytics-and-call-quality-dashboard.md)

-   [Utiliser l’analyse des appels pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)

### <a name="call-analytics-support"></a>Appelez le support technique Analytique

-   Communauté : [Skype pour le programme Aperçu](https://techcommunity.microsoft.com/t5/Skype-for-Business-Preview/bd-p/SkypeforBusinessPreviewProgram)

-   Pour obtenir une assistance, connectez-vous à notre portail de preview [www.skypepreview.com](http://www.skypepreview.com), sélectionnez **un problème de rapport**et utiliser l’option **Créer un nouveau bogue** pour signaler un problème. Veuillez noter que les techniciens du support technique sont disponibles pour prendre en charge du lundi au vendredi, entre 6 h et 9 h fuseau horaire (États-Unis). Demandes en dehors de ces heures triage seront le jour suivant.

### <a name="devices"></a>Appareils

-   [Skype pour Business Solutions catalogue périphériques personnels & PC](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

### <a name="tenant-reporting"></a>Création de rapports de client

-   [Pack de contenu Office 365 d’Adoption](https://www.microsoft.com/microsoft-365/blog/2017/05/22/announcing-the-public-preview-of-the-office-365-adoption-content-pack-in-powerbi/)

-   [Analyse de l'utilisation de Microsoft 365](https://support.office.com/article/Microsoft-365-usage-analytics-77ff780d-ab19-4553-adea-09cb65ad0f1f)

-   [Création de rapports Skype Entreprise Online](/SkypeForBusiness/skype-for-business-online-reporting/skype-for-business-online-reporting)

-   [Microsoft Teams création de rapports](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/New-usage-reports-for-Microsoft-Teams/ba-p/132614)
