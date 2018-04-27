---
title: Qualité de consulter le Guide de l’expérience pour les équipes Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 04/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Guide pour l’analyse des performances de médias en temps réel pour Microsoft Teams à l’aide du tableau de bord de la qualité des appels (CQD).
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f0f5eb9ff2521d56214a9e07be715da21a5bed3
ms.sourcegitcommit: 5cc51e2d3898fccd1969accedb5e185a332e83bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2018
---
# <a name="quality-of-experience-review-guide"></a>Qualité de consulter le Guide de l’expérience

Ce guide est à la phase de valeur lecteur pour Microsoft Teams et Skype pour Business Online. Vous pouvez [télécharger une version de Word](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) de ce guide.

## <a name="introduction"></a>Introduction

Pour que le plus grand impact sur l’amélioration de l’expérience utilisateur, les organisations doivent mettre les zones clés qui sont indiquées dans la figure suivante.
Des zones supplémentaires incluent identifiant les tâches opérationnelles, établir les objectifs de mesures de qualité, déterminer les mesures à utiliser pour évaluer le succès de l’organisation et limiter les zones d’enquête selon vos besoins.

![Zones clés pour la qualité de l’expérience utilisateur incluent les paramètres audio, la fiabilité, les enquêtes effectuées auprès, clients et appareils.](media/quality-of-experience-review-guide-image1.png)

_Figure 1 : zones opérationnelles clé couvertes dans ce document_

En permanence évaluer et corriger les zones décrites dans ce document, vous pouvez réduire leur potentiel pour un impact négatif sur la qualité de l’expérience de vos utilisateurs. La plupart des problèmes d’expérience utilisateur dans un déploiement peuvent être regroupées dans les catégories suivantes :

-   Configuration de pare-feu ou proxy incomplète

-   Une mauvaise couverture Wi-Fi

-   Bande passante insuffisante

-   VPN

-   Versions du client incohérents ou obsolètes

-   Périphériques audio non optimisées ou intégrés

-   Sous-réseaux problématiques ou périphériques réseau

Via une planification et conception avant de déployer des équipes ou Skype pour Business Online, vous pouvez réduire le volume de travail qui est requis pour maintenir une expérience de haute qualité.

Ce guide se concentre sur l’utilisation en ligne du tableau de bord de la qualité des appels (CQD) comme le principal outil pour signaler et examiner chaque zone, avec un accent sur son adoption et impact. Les améliorations apportées au réseau pour améliorer l’expérience audio auront également directement des améliorations dans le partage du bureau et vidéo.

Pour accélérer votre évaluation, deux modèles CQD curated sont fournies : une pour la gestion de tous les réseaux et l’autre est filtrée (internes) les réseaux gérés uniquement. Bien que les modèles de rapport de tous les réseaux sont configurés pour afficher des informations de réseau et de création, il peut toujours être utilisé lorsque vous travaillez vers la collecte et de chargement des informations de construction. Téléchargement d’informations en CQD permet au service améliorer la création de rapports en ajoutant les informations de création, le réseau et emplacement personnalisées lors de la différenciation interne à partir de sous-réseaux externes. Pour plus d’informations, voir [mappage de création](#building-mapping) plus loin dans ce document.

### <a name="what-is-the-cqd"></a>Quel est le CQD ?

Le tableau de bord de qualité des appels (CQD) vous permet de comprendre la qualité des appels effectués à l’aide des équipes et Skype pour les services. CQD est conçu pour aider à Skype pour les administrateurs d’entreprise et les équipes et optimisent le réseau les ingénieurs réseau. CQD examine compilent les informations pour toute une organisation où les modèles globales peuvent devenir apparentes, permettant le personnel à évaluer informé de la qualité des appels. CQD fournit des rapports de mesures d’appel que vous donnent une idée globale la qualité des appels, la fiabilité des appels et expérience utilisateur.

> [!NOTE]
> CQD ne contient pas les informations d’identification personnelle (PII). Informations d’identification personnelle sont informations pouvant être utilisées sur son propre ou avec d’autres informations pour identifier, de contacts ou de localiser une seule personne, ou pour identifier une personne dans le contexte. 

### <a name="intended-audience"></a>Audience ciblée

Ce document est destiné à être utilisé par les parties prenantes de partenaires et des clients avec les rôles de Collaboration/architecte en chef, Consultant, spécialiste des modifications gestion / d’Adoption, entraîner de support technique, câble réseau, bureau conduire et administrateur informatique

Ce document est également destiné à être utilisé par le champion(s) qualité désignés.
Pour plus d’informations, voir [le rôle Champion de qualité](https://docs.microsoft.com/MicrosoftTeams/4-envision-plan-my-service-management#the-quality-champion-role).

## <a name="prerequisites"></a>Conditions requises

Avant d’utiliser ce guide, assurez-vous que vous avez le client appropriée les [rôles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) affectés afin que vous puissiez accéder CQD.

-   **Rôle Administrateur général de office 365 :** Accède à toutes les fonctionnalités d’administration de la suite Office 365 des services dans votre plan, y compris Skype pour les entreprises.

-   **Skype pour le rôle d’administrateur :** Configure Skype pour les entreprises pour votre organisation et est en mesure d’afficher tous les [rapports d’activité](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) dans le centre d’administration d’Office 365. Ce rôle est nécessaire, même si vous déployez uniquement les équipes.

Autrement, vous pouvez affecter le rôle suivant à un compte d’utilisateur Office 365 pour autoriser l’accès aux fonctionnalités de création de rapports uniquement.

-   **Rapports lecteur :** Peuvent afficher tous les [rapports d’activité](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) dans le centre d’administration Office 365, les rapports à partir du [pack de contenu Office 365 Adoption](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)et des rapports CQD.

Comprendre les concepts clés de CQD vous aide à optimiser l’impact que vous permettent d’améliorer l’expérience de vos utilisateurs avec des équipes ou Skype pour Business Online.
Vous trouverez des ressources supplémentaires dans l' [annexe](#other-resources).

## <a name="what-is-quality"></a>Quelle est la qualité ?

Lorsque vous abordez qualité dans Skype pour les entreprises et les équipes, il est important de définir le terme pour obtenir une présentation courants. Qualité, tel que défini ici, est une combinaison de l’expérience utilisateur et de mesures de service.

![Mesures de service sont composés des versions appels médiocres taux, la fiabilité, les points de terminaison/appareils et client. L’utilisateur final est composée de perception de l’utilisateur de la qualité de service.](media/quality-of-experience-review-guide-image2.png)

_Figure 2 : quelle est la qualité ?_

### <a name="define-your-target-metrics"></a>Définir votre mesures cible

Cette section décrit les mesures de service principaux que nous utilisons pour évaluer comment services expérience d’intégrité. Par continuellement évaluer et conduite efforts de garder ces mesures ci-dessous cible, vous allez garantir que la qualité des appels de façon cohérente et fiable heurter à vos utilisateurs. Pour vous aider, les objectifs suivants sont fournis.
Nous allons brièvement la différence entre un réseau géré et non géré :

-   Un réseau *géré* pouvant être influencé et contrôlé par l’organisation.
    Cela inclut le réseau interne, le réseau étendu à distance et VPN.

-   Un réseau *non géré* ne peut pas être influencé ou contrôlé par l’organisation. Un exemple d’un réseau non géré est un réseau d’hôtel ou un aéroport.

_Tableau 1 : mesures d’évaluation principaux cible d’intégrité_

|               | Qualité pour les réseaux gérés | Fiabilité pour les réseaux gérés |                      |
|---------------|------------------------------|----------------------------------|----------------------|
| Nom de métrique   | % De taux d’appel audio médiocre      | Appeler le programme d’installation % d’erreurs            | Appel de dépôt % d’erreurs |
| Cible de l’exemple | \<% 3                         | \<1 %                             | \<4 %                 |

Il est important de discuter et définir les objectifs de votre organisation pour répondre aux objectifs de votre entreprise. Idéalement, vous devez identifier ces cibles avant le déploiement.

#### <a name="audio-pcr-"></a>% PCR audio 

Audio médiocre appeler taux (PCR) représente le pourcentage global de l’organisation des appels qui ont une mauvaise qualité audio. Cette mesure vise à mettre en surbrillance les zones où votre organisation peut se concentrer afin d’affecter le plus élevé en réduisant cette valeur et améliorer l’expérience utilisateur, c’est pourquoi les réseaux gérés sont le principal objectif lorsque vous examinez PCR. Les utilisateurs externes sont trop importants, mais diffère des enquêtes sur une base d’utilisateur et d’organisation.
Envisager de renvoyer des meilleures pratiques pour les utilisateurs externes, puis examinez les appels externes indépendamment de l’entreprise globale.

#### <a name="call-setup-failures-"></a>Appeler le programme d’installation % d’erreurs 

Il s’agit d’une session multimédia qui n’ont pas pu être établie. La gravité de l’impact sur l’expérience utilisateur mesurée ici, l’objectif consiste à réduire cette valeur comme proches de zéro que possible. Une valeur élevée pour cette mesure est plus fréquente dans les nouveaux déploiements avec des règles de pare-feu incomplète qu’un déploiement évolué, mais il est important de regarder régulièrement. Comme votre rigueur opérationnel ailleurs, vous pouvez développer cette mesure pour inclure des charges de travail vidéo et partage du bureau.

#### <a name="call-drop-failures-"></a>Appel de dépôt % d’erreurs 

Cela s’applique à une charge de travail audio où la session s’est arrêté inopinément. Comme votre rigueur opérationnel ailleurs, vous pouvez développer cette mesure pour inclure des charges de travail vidéo et partage du bureau.

### <a name="service-metrics"></a>Mesures de service

Objectifs de métriques de service se composent des mesures basée sur le client spécifiques.

#### <a name="pcr"></a>PCR

Pour déterminer si un appel est classé comme médiocre est en utilisant le taux d’appels médiocres (PCR). PCR se compose des cinq mesures réseau décrites dans le tableau suivant. Pour un appel à être classé comme médiocre, qu’une mesure doit dépasse le seuil défini. Pour plus d’informations sur le processus de classification des appels, consultez [ce billet de blog](https://blogs.technet.microsoft.com/jenstr/2013/09/20/what-is-the-basis-for-classifying-a-call-as-poor-in-lync-2013-qoe/).

_Tableau 2 - mesures de Service d’appels médiocres_

| Mesure                                           | Description                                                                                                                                                                                                                                                                                                                                                                  | Expérience utilisateur                                                                                                                                                          |
|--------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Gigue \>30 ms                                   | Il s’agit de la variation moyenne de retard entre les paquets successives. Les équipes et Skype pour les entreprises peuvent s’adapter à certains niveaux de gigue par le biais de mise en mémoire tampon. Il est uniquement lorsque la gigue dépasse la mise en mémoire tampon un participant d’avertissements les effets de gigue.                                                                                                                         | Les paquets arrivant à différentes vitesses provoquent voix d’un haut-parleur à son automatisée.                                                                                       |
| Taux de pertes de paquets \>0,1 ou 10 %                    | Il est souvent définie sous forme de pourcentage des paquets sont perdus. Perte de paquets affecte directement la qualité audio, à partir de petite, individuel paquets perdus qui n’ont presque aucun impact pertes rafale DOS à DOS que la fonctionnalité audio cause découper complètement.                                                                                                                               | Les paquets en cours perdus et d’arriver pas à leur destination entraîner des écarts dans le support, qui en résulte dans des mots et syllabes manqués et saccadé vidéos et de partage. |
| Temps d’aller-retour \>500 ms                         | Il s’agit du temps que nécessaire pour obtenir un paquet IP à partir d’un point à point B et au point A. Ce délai de propagation de réseau est lié à la distance physique entre les deux points et la vitesse de la lumière et inclut une surcharge supplémentaire prise par les différents périphériques dans le chemin d’accès réseau.                                                                                  | Les paquets prend trop de temps pour parvenir à sa destination provoquent un effet talkie-walkie.                                                                                 |
| Moyenne de dégradation NMOS \> 1.0                  | Une ou plusieurs de ces mesures réseau, individuellement n’ont pas été médiocre, ensemble due la [Moyenne d’opinion](https://technet.microsoft.com/library/bb894481(v=office.12).aspx) de réseau (NMOS) pour supprimer plusieurs points. Cela ne signifie pas nécessairement la connexion réseau est faible, mais suffisamment problèmes s’est produite pendant l’appel que qualité a été réduite. | Il s’agit d’une combinaison de gigue, la perte de paquets, et, dans une moindre mesure : augmenter le temps d’aller-retour. L’utilisateur peut être confronté à une combinaison de ces problèmes.          |
| Taux moyen d’échantillons \> 7 % ou 0,07 | Une ou plusieurs de ces mesures réseau, individuellement n’ont pas été médiocre, a provoqué le client à autoréparation du média. Un échantillon audio masqué est une technique utilisée pour atténuer les la transition brutale doit généralement être provoquée par paquets perdus.                                                                                                                | Des valeurs élevées indiquent que des niveaux significatifs de masquage de perte ont été appliquées et a provoqué audio déformé ou perdue.                                                  |

#### <a name="client-and-device-readiness"></a>Préparation des clients et périphériques

Vous avez besoin d’une stratégie de client et des périphériques solide pour vous assurer que vos utilisateurs une expérience utilisateur positive et cohérente. Chaque stratégie de préparation du lecteur quelques principes clés.

##### <a name="client-readiness"></a>Préparation du client

Une stratégie de disponibilité du client fort garantit que vos utilisateurs exécutent la version la plus récente du client tout en profitant le meilleur parti.
Microsoft correctifs régulièrement la Skype pour client d’entreprise ; en vous assurant que vous maintenir à jour dans votre environnement est essentiel pour votre réussite globale.

Nous vous recommandons de pas laisser votre versions du client comprises en plus de six mois. Si vous utilisez Office Click-to-Run, vous êtes déjà en cours mis à jour par le service. Utilisez le inclus [Rapport du Client](#determine-client-versions), comme décrit plus loin dans ce guide, pour vous aider dans ce processus. Vous pouvez également exploiter les exemples de rapports taux mon appel à améliorer votre stratégie de disponibilité du client.

> [!IMPORTANT]
> Actuellement, les équipes clients sont distribués et mis à jour automatiquement via le réseau de livraison de contenu Azure et seront conservés à jour par le service. Préparation des clients et activités investigation ne sont pas applicables aux équipes.


##### <a name="device-readiness"></a>Préparation du périphérique

Aucune une stratégie unique ne peut affecter l’expérience utilisateur plus de votre stratégie de disponibilité du périphérique. La plupart des organisations sont satisfaites supprimer les périphériques inutiles d’utilisateurs (par exemple, téléphones de bureau ou d’autres périphériques audio dédiées), et il s’agit souvent une justification principaux de passage à des équipes ou Skype pour les entreprises. Toutefois, ces organisations même parfois hésitent pas à fournir des périphériques de remplacement, même si ces périphériques sont moins onéreux. Ordinateurs portables moderne et PC, mais équipés de microphone et haut-parleur, intégrés ne sont pas optimisés pour professionnelles voix sur IP (VoIP). Cela crée souvent une mauvaise expérience pour tous les participants, en particulier si le haut-parleur est dans un environnement de bruit. Programme de certification de périphériques de Microsoft garantit que lorsqu’un utilisateur participe à un appel téléphonique à l’aide de n’importe quel appareil certifié pour les équipes ou Skype pour les entreprises, elle génère une expérience est supérieure à un périphérique non certifiés.

Nous vous recommandons toujours que Skype pour les utilisateurs professionnels et les équipes utilisent un casque certifié ou les haut-parleurs lorsque vous participez à un appel vocal à l’aide d’un client de bureau.
Pour plus d’informations sur les périphériques certifiés de Microsoft, lisez cet [article sur les téléphones et appareils qualifiés](https://technet.microsoft.com/office/dn788944.aspx). Utilisez le [Rapport de périphérique](#devices-investigations), plus loin dans ce guide, pour l’aide à la gestion de vos périphériques. Vous pouvez également utiliser les exemples de rapports taux mes appels pour améliorer votre stratégie de disponibilité du périphérique.

### <a name="user-experience"></a>Expérience utilisateur

Analyse de l’expérience utilisateur est plus art qu’une science, les mesures collectées ici ne toujours parce qu’il existe un problème avec le réseau ou le service, mais plutôt qu’ils indiquent que l’utilisateur détecte un problème. Microsoft propose un mécanisme d’enquête intégrée — connus en tant que taux mon appel (RMC) — pour aider à évaluer l’expérience utilisateur globale. RMC va vous aider à répondre aux questions suivantes à partir du point de vue de vos utilisateurs :

-   Savoir comment utiliser la solution ?

-   Est la solution facile à utiliser et intuitive, et ne prend en charge mes besoins en communication quotidienne ?

-   Est la solution m’aider à faire mon travail ?

-   Quel est mon perception globale de la solution ?

-   Puis-je utiliser la solution à tout moment dans le temps, quel que soit l’où je suis ?

-   Puis-je configurer et maintenir un appel ?

#### <a name="rmc"></a>RMC.

RMC est intégré dans les équipes et Skype pour les entreprises et est automatiquement configuré pour être affiché après une dans tous les 10 appels ou 10 pour cent de tous les appels. Ce bref questionnaire invite l’utilisateur à évaluer l’appel et fournissent un contexte peu pour pourquoi la qualité des appels ont pu médiocre. Une évaluation d’un ou deux est considéré comme une mauvaise, trois ou quatre est correcte et cinq est considérée comme excellente. Bien qu’il soit un peu d’un indicateur à cause du retard, il s’agit d’une mesure utile pour les problèmes découvrant les mesures de service peuvent être manquantes.

> [!NOTE]
> Jusqu'à ce que les utilisateurs sont invités à répondre aux enquêtes RMC en donnant une bonne commentaires en plus de réponses incorrects, généralement revenir comme extrêmement négative. La plupart des utilisateurs répondront uniquement lorsque la qualité des appels est faible. Pour cette raison, vos rapports RMC peuvent être oblique sur le côté une mauvaise même si des mesures de service sont corrects. 


Vous pouvez utiliser CQD pour créer des rapports sur les réponses de l’utilisateur RMC et exemples de rapports sont inclus dans le modèle CQD. Toutefois, elles ne sont pas présentées en détail dans ce guide. Pour plus d’informations sur RMC dans Skype pour Business Online et conseils pour la formation des utilisateurs pour donner des réponses RMC utiles, consultez le [billet de blog](https://blogs.technet.microsoft.com/jenstr/2015/05/05/rate-my-call-in-skype-for-business-2015/).

### <a name="categories-of-quality"></a>Catégories de qualité

La réussite d’un déploiement de haute qualité et fiable à mettre en application dépend de votre rigueur opérationnelles de construction. Plus précisément, une attention particulière aux trois catégories illustré dans la figure suivante ; Il s’agit de l’objectif de ce guide :

-   **Réseau :** Qualité audio axés sur le système métrique PCR, l’utilisation TCP, sous-réseaux avec et sans fil et l’identification de l’utilisation de VPN et les proxys HTTP.

-   **Points de terminaison :** Périphériques audio et la version du client (Skype pour les entreprises uniquement).

-   **Gestion des services :** Cette catégorie comprend deux sections :

    -   Tout d’abord incombe de Microsoft pour gérer et tenir à jour les équipes et Skype pour Business Online services.

    -   Deuxième sont les tâches de que votre organisation doit gérer pour garantir un accès fiable au service, telles que la mise à jour des informations de création et maintenance de pare-feu pour le nouvel Office 365 adresses comme infrastructure est ajoutée au service.

![Les catégories de qualité dans une organisation : service de gestion, les systèmes d’extrémité et le réseau.](media/quality-of-experience-review-guide-image3.png)

_La figure 3 - catégories critiques pour les équipes et Skype pour le déploiement d’entreprise en ligne_

Le graphique ci-dessous présente les tâches que vous devez exécuter pour chaque catégorie. Nous vous conseillons d’exécuter ces tâches une fois par semaine, au minimum.

La première fois que vous effectuez ces tâches prendra plus d’effort que des itérations suivantes, car la plupart des catégories suivantes nécessitent que vous validez les configurations de votre déploiement. Une fois que vous avez réalisé l’état souhaité en réunion cibles que vous avez définie, exécution de ces tâches vous aideront à mettre à jour cet état.

#### <a name="service-management-tasks"></a>Tâches de gestion de service

Dans un environnement cloud d’abord, vous devez effectuer certaines tâches de gestion de service pour maintenir une expérience utilisateur de qualité. Ces tâches comprise, garantissant la bande passante est suffisante pour atteindre le service sans saturer les liaisons internet, validation de qualité de service (QoS) est en place sur tous les domaines de réseau géré, et, enfin, face à [Office 365 IP plages sur pare-feu](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).

#### <a name="network-tasks"></a>Gestion du réseau

Il existe deux catégories de gestion du réseau : la fiabilité et la qualité. La fiabilité se concentre sur la mesure de la capacité de l’utilisateur à passer des appels avec succès et restez connecté. Qualité se concentre sur la télémétrie agrégée envoyé aux équipes et Skype pour Business Online par le client de l’utilisateur pendant et après avoir terminé l’appel.

Étant donné l’impact majeur de fiabilité sur l’expérience utilisateur, commencer à évaluer et rechercher ces mesures avant de plonger dans qualité.

#### <a name="endpoints-tasks"></a>Tâches de points de terminaison

La principale tâche de cette catégorie valide les versions du client sont en cours d’exécution Skype pour les entreprises sur les builds de bureau à partir de six derniers mois pour garantir les utilisateurs obtiennent l’avantage des optimisations continues apportées à la Skype pour le client de bureau d’entreprise. En outre, simplifie les tâches de gestion globale du client et fournit une expérience utilisateur cohérente.

La zone autres importante est analyse les périphériques sont courants dans votre déploiement et l’utilisation de périphériques certifiés pour fournir la meilleure expérience utilisateur de commande.

> [!IMPORTANT]
> Actuellement, les équipes clients sont distribués et mis à jour automatiquement via le réseau de livraison de contenu Azure et seront conservés à jour par le service. Préparation des clients et activités investigation ne sont pas applicables aux équipes.


## <a name="using-the-reports"></a>Utilisation des rapports

Cette section décrit les concepts fondamentaux de l’utilisation de CQD. Est fournie pour les rubriques suivantes :

-   Recherche de votre ID client

-   Création de rapports sur les équipes et Skype pour les entreprises

-   Première et deuxième classifications

-   Mesures, dimensions et des filtres

-   Flux de données par rapport à des appels

-   Appels non classés, bonne et médiocres

-   Mise en route avec CQD

-   Modification de rapports dans CQD

-   Le filtrage des rapports dans CQD

Pour plus de formations et de ressources, voir l' [annexe](#other-resources).

### <a name="tenant-id"></a>ID de client

Certains rapports CQD nécessitent que vous incluez un filtre pour votre ID de client. En raison de la manière de que CQD regroupe les données télémétrie participant fédéré est inclus.
Bien que cela peut s’avérer utile lors de l’analyse des mesures d’appels médiocres, rapports de client et des périphériques nécessitent le filtrage de données à un client spécifique à exclure télémétrie participant fédéré. Si vous ne connaissez pas votre ID client, vous pouvez utiliser une des méthodes suivantes pour le trouver.

Autorisations requises

-   Rôle d’administrateur global

-   Skype pour le rôle d’administrateur

#### <a name="azure-ad-portal"></a>Portail d’Azure AD

1.  Connectez-vous au portail Microsoft Azure :<https://portal.azure.com>

2.  Sélectionnez **Azure Active Directory**.

3.  Sous **Manage**, sélectionnez **Propriétés**. L’ID client est indiqué dans la zone **ID de répertoire** .

#### <a name="azure-powershell"></a>Azure PowerShell

1.  [Installer le module de gestion des services Microsoft Azure PowerShell](https://docs.microsoft.com/powershell/azure/servicemanagement/install-azure-ps?view=azuresmps-4.0.0).

2.  Ouvrez une fenêtre de commande Windows Azure PowerShell et exécutez le script suivant, entrez vos informations d’identification Office 365 à l’invite :  
    **Connexion-AzureRmAccount**

3.  L’ID de client est répertorié dans la sortie.

#### <a name="skype-for-business-online-admin-center"></a>Skype Business Online Centre d’administration

1.  Atteindre<https://portal.office.com>

2.  Connectez-vous avec votre compte d’administrateur client d’organisation.

3.  Sélectionnez **Skype pour les entreprises** sous **Centres d’administration**.

4.  L’ID de client est répertorié en tant **qu’ID de l’organisation** sur la page d’accueil.

#### <a name="skype-for-business-online-using-powershell"></a>Skype pour Business Online à l’aide de PowerShell

1.  [Se connecter à Skype pour les entreprises en ligne via PowerShell](https://technet.microsoft.com/library/dn362839(v=ocs.15).aspx).

2.  Exécutez la commande suivante :  
    **.Tenantid (get-cstenant)**

3.  L’ID de client est affiché sous forme de GUID.

### <a name="teams-vs-skype-for-business"></a>Équipes et Skype pour les entreprises

CQD peut créer des rapports sur les équipes et Skype pour télémétrie Business. Toutefois, il peut arriver que lorsque vous souhaitez développer un rapport d’examiner télémétrie équipes distinct Skype pour les entreprises.

#### <a name="summary-reports"></a>Rapports de synthèse

Pour modifier la page de rapports de synthèse pour consulter uniquement les équipes ou Skype pour les entreprises, sélectionnez le menu déroulant de **Filtre de produit** à partir du haut de l’écran, puis sélectionnez le produit que vous souhaitez.

![Capture d’écran de l’appel tableau de bord qualité reflétant une liste déroulante affichant l’option de filtrage par charge de travail.](media/quality-of-experience-review-guide-image4.png)

_Figure 4 : sélectionner un filtre de produit_

#### <a name="detailed-reports"></a>Rapports détaillés

Pour filtrer un rapport détaillé, ajoutez le filtre **Équipes est** à l’état et affectez-lui la valeur True ou False. Pour plus d’informations, consultez [modification des rapports](#editing-reports) plus loin dans cette section.

![Capture d’écran de l’appel tableau de bord qualité représentant le serveur de fichiers qui peut être ajouté à un rapport détaillé.](media/quality-of-experience-review-guide-image5.png)

_Figure 5 : ajout d’un filtre Teams Microsoft à un rapport_

### <a name="dimensions-measures-and-filters"></a>Mesures, dimensions et des filtres

Une requête CQD correcte contienne les trois paramètres suivants :

-   **Dimension :** Comment faire sur les données de tableau croisé dynamique.

-   **Mesure :** Je veux créer un rapport.

-   **Filtre :** Comment souhaitez-vous afin de réduire la requête renvoie le jeu de données.

Une autre façon de concevoir le système est une dimension est la fonction de regroupement, une mesure est les données que m’intéresse et un filtre, c’est comment limiter les résultats à ceux qui sont pertinents pour ma requête.

Un exemple de requête correct est « me faire une mauvaise flux [mesures] par sous-réseau [Dimension] pour la génération 6 [filtre]. »

Pour plus d’informations, voir [Dimensions et mesures disponibles dans CQD](https://aka.ms/cqd-dm).

Pour les dimensions, les mesures et des filtres pour les rapports utilisés dans les modèles CQD, voir l' [annexe](#CQD-training).

### <a name="first-vs-second"></a>Première et deuxième 

La plupart des dimensions et mesures CQD sont classées comme première ou deuxième.
CQD n’utilise pas de champs de l’appelant/appelé, ils ont été renommées _premier_ et _deuxième_ car il existe des étapes intermédiaires entre l’appelant et l’appelé. La logique suivante détermine quel point de terminaison du flux ou de l'appel est étiqueté comme premier :

-   Tout d’abord sera toujours un point de terminaison de serveur (serveur de conférence, le serveur de médiation et ainsi de suite) si un serveur est impliqué dans le flux ou d’un appel.

-   Deuxième sera toujours un point de terminaison client, sauf si le flux est entre deux points de terminaison de serveur.

-   Si les deux points de terminaison sont le même type, le choix d’est la première est basé sur le classement interne de la catégorie de l’agent utilisateur. Cela garantit la cohérence de l'organisation.

Pour plus d’informations sur la détermination de la première ou deuxième point de terminaison lorsqu’ils sont identiques, voir [Dimensions et mesures disponibles dans CQD](https://aka.ms/cqd-dm).

### <a name="stream-vs-call"></a>Flux de données et l’appel

Vous devez comprendre la différence entre un appel et d’un flux correctement choisir lequel les dimensions ou mesures vous examinerons dans CQD.

**Flux :** Il existe un flux entre deux points de terminaison. Il existe un seul flux pour chaque direction et deux flux sont requis pour la communication. Les flux sont utiles pour analyser les bâtiments ou des réseaux. Dans certains cas, appel et flux sont utilisés dans le nom (par exemple, flux de configuration des appels ou appel ignorés flux).
Ils sont toujours classés en tant que flux uniques.

**Appel :** Un appel est un regroupement de tous les flux de tous les participants. Un appel se compose de : au minimum, deux flux. Un seul appel aura deux participants avec un minimum d’un flux de données. Les appels sont utiles pour l’analyse des tendances au fil du temps.

Pour obtenir des instructions supplémentaires sur si la dimension ou mesure fait référence à un appel ou un flux de données, voir [Dimensions et les mesures disponibles dans CQD](https://aka.ms/cqd-dm)

### <a name="good-poor-and-unclassified-calls"></a>Appels non classés, bonne et médiocres

Un appel est classé comme bonne, mauvaise, soit non classés. Prenons un moment pour parler plus en détail chacune d’elles.

**Bonne ou mauvaise :** Un appel de bonne ou mauvaise se compose d’un appel qui contient un ensemble complet des mesures de service, pour lequel un rapport QoE complet a été généré.
Pour déterminer si un appel est une bonne ou une mauvaise est décrit [plus haut dans ce guide](#pcr).

**Non classés :** Un appel non classé ne contient pas un ensemble complet des mesures de service. Il s’agit souvent de courtes appels — généralement inférieure à 60 secondes — où moyennes n’ont pas pu être calculées et un rapport QoE n’a pas été créé.

### <a name="access-cqd-online"></a>Accès CQD

Vous pouvez accéder CQD de deux façons.

-   Accédez à <https://cqd.lync.com>.

-   Accédez à **Skype pour le centre d’administration Business** \> **Outils**, puis sélectionnez le lien vers CQD, comme indiqué ci-dessous.

![Capture d’écran indiquant « outils » est sélectionnés dans le volet de navigation de gauche et le lien vers « Skype pour Business Online appeler tableau de bord qualité » sélectionnée.](media/quality-of-experience-review-guide-image6.png)

_La figure 6 – accès CQD via le Skype entreprise centre d’administration_

### <a name="getting-started"></a>Prise en main

Lorsque vous accédez d’abord à CQD, vous verrez la page Rapports de synthèse. La plupart des rapports décrits dans ce guide sont des rapports détaillés personnalisés. Pour commencer à utiliser des rapports détaillés, sélectionnez **Rapports de synthèse** dans la partie supérieure de la page, puis choisissez **Des rapports détaillés**.

![Capture d’écran de l’appel du tableau de bord qualité depcting les différents types de rapports qui sont disponibles.](media/quality-of-experience-review-guide-image7.png)

_Figure 7 : naviguer vers des rapports détaillés_

La page Rapports détaillés dans CQD ressemble à la figure ci-dessous.

![Capture d’écran de la page rapport détaillé dans CQD et les différents éléments qui constituent un rapport.](media/quality-of-experience-review-guide-image8.png)

_Figure 8 : page de rapports détaillés_

1.  Le volet Résumé affiche le contexte pour le jeu de rapport qui s’affiche à droite.

2.  Vous pouvez sélectionner **Modifier** dans le volet Résumé pour définir les propriétés au niveau de rapport (y compris la hauteur de l’axe des y).

3.  La barre de navigation permet aux utilisateurs d’identifier leur emplacement actuel dans la hiérarchie du jeu de rapport.

4.  Rapports possédant des rapports enfants sont affichés avec un lien bleu. En cliquant sur le lien, vous pouvez accéder à le rapports enfant.

Pointez sur les graphiques à barres et les courbes de tendance pour afficher les valeurs détaillées. L’état qui a le focus affiche le menu action : **Modifier**, **Clone**, **Supprimer**, **Télécharger**et **Exporter arborescence du rapport**.

### <a name="editing-reports"></a>Modification de rapports

Lorsque vous sélectionnez **Modifier** dans le menu action d’un état, vous devez ouvrir l’éditeur de requête. Chaque rapport est sauvegardée par une requête. Il s’agit de la visualisation des données renvoyées par la requête. L’éditeur de requête est une interface utilisateur pour la modification de ces requêtes outre les options d’affichage pour le rapport, comme illustré dans la figure suivante.

![Capture d’écran de la page rapport détaillé dans CQD et les différents éléments qui constituent un rapport lorsque le rapport est en cours de modification.](media/quality-of-experience-review-guide-image9.png)

_Figure 9 : éditeur de rapport_

1.  Vous choisissez mesures, dimensions et des filtres dans le volet gauche. Pointez sur une valeur existante affiche un bouton Fermer (**X**), que vous pouvez sélectionner pour supprimer la valeur.

    1.  En sélectionnant la dimension ou mesure, vous pouvez modifier le titre en modifiant le champ **titre** . Vous pouvez également modifier l’ordre en sélectionnant le bleu monter ou Descendre flèches dans le volet supérieur.

    2.  Sélection (**+**) en regard d’un en-tête de la boîte de dialogue pour ajouter une nouvelle dimension, une mesure ou un filtre.

    3.  Entrez les premières lettres de la dimension, une mesure ou un filtre dans la **trouver un** champ pour filtrer la liste de recherche.

2.  Le volet supérieur présente les options de personnalisation de graphique.

3.  L’éditeur de requête affiche un aperçu du rapport.

4.  Utilisez la zone **Modifier** au bas de l’écran pour créer ou modifier une description détaillée du rapport.

### <a name="filtering-reports"></a>Le filtrage des rapports

Les modèles fournis inclut plusieurs requêtes intégrées et les filtres du rapport. Les sections suivantes décrivent les filtres les plus courants utilisés dans les modèles.

#### <a name="cqd-filter"></a>Filtre CQD

Vous pouvez utiliser le filtre CQD ou le filtre d’URL, filtrer temporairement chaque requête d’état. Le filtre CQD les plus courantes que vous allez utiliser consiste à filtrer les rapports à exclure de télémétrie participant fédéré. Nous vous recommandons de signet ce filtre afin qu’il devienne l’affichage par défaut. À l’exclusion de données fédérées à partir des rapports CQD est utile lorsque vous êtes couronnée de bâtiments gérées ou des réseaux où les données fédérées peuvent influencer votre rapport.

Pour implémenter un filtre CQD, dans la barre Adresse du navigateur, ajoutez le code suivant à la fin de l’URL :

/Filter/ [AllStreams]. [Id de client deuxième] \|[Votre ID client ici]

**Exemple :**  
https://cqd.lync.com/cqd/\#/-1234567/2018 02/filtre / [AllStreams]. [Id de client deuxième] \|[ID client sur] & client = ID client sur

> [!NOTE]
> L’exemple d’URL est pour une représentation visuelle uniquement. Utilisez le lien CQD par défaut de <https://cqd.lync.com>.

#### <a name="query-filters"></a>Filtres de requête

Filtres de requête sont implémentées à l’aide de l’éditeur de rapport. Ces filtres sont utilisés pour réduire le nombre d’enregistrements renvoyés par CQD, ce qui réduit la taille globale de l’état. Ceci est particulièrement utile pour le filtrage des réseaux non managés.
Les filtres ci-dessous utilisent des expressions régulières (RegEx).

_Tableau 3 - filtres de requête_

| Filtre               | Description          | Exemple de filtre de requête CQD                                  |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|
| Valeurs non renseignées         | Certains filtres n’ont l’option de filtrage pour les valeurs vides. Pour filtrer les valeurs vides manuellement, utilisez l’expression vide et la valeur du filtre est égal à ou pas égal à, selon vos besoins.                                                                                                                             | Nom de la construction de la seconde \< \> \^ \\s\*\$                       |
| Sous-réseaux personnel populaires | Sans un fichier construction valide pour séparer gérés à partir de réseaux non gérés, réseau domestique système incluses dans les rapports. Ces sous-réseaux personnel se trouvent en dehors de l’étendue de son contrôle et peut être exclus rapidement un rapport. Sous-réseaux personnel populaires, comme défini dans ce guide, sont 10.0.0.0, 192.168.1.0 et 192.168.0.0. | Deuxième sous-réseau \< \> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Interne et externe   | Utilisé pour filtrer un rapport (interne) managé ou non managé (externe). Le modèle CQD géré est déjà préconfiguré avec ces filtres.                                                                                                                                                                                | Seconde à l’intérieur de Corp = à l’intérieur                               |

#### <a name="report-filters"></a>Filtres du rapport

Filtres du rapport sont implémentées en ajoutant un filtre pour le rapport rendu soit dans l’éditeur de rapport ou directement à l’état. Les filtres de rapports suivants sont utilisés dans le modèle.

_Tableau 4 : filtre du rapport_

| Filtre     | Description                            | Exemple de filtre de rapport CQD         |
|------------|----------------------------------------|-----------------------------------|
| Month      | Démarrer avec l’année en premier, puis les mois. | 2017-10                           |
| Alphabétique | Filtres pour les caractères alphabétiques. | [a-z]                             |
| Numérique    | Filtres pour n’importe quel caractère numérique.    | [0-9]                             |
| Pourcentage | Filtre un pourcentage.              | ([3-9]\\.) \|([3-9])\|([1-9][0-9]) |

## <a name="import-the-cqd-templates"></a>Importer les modèles CQD

Ce guide inclut [deux modèles CQD curated](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-lite-templates-v-1-2.zip?raw=true). Ces modèles accélèrent votre utilisation de CQD et vous permettent de rapidement tirer parti des fonctionnalités de CQD un impact sur vos utilisateurs des équipes ou Skype pour une expérience. Le modèle de tous les réseaux, mais optimisé pour fonctionner avec une création de fichier de données, peut être utilisé lorsque vous travaillez à collecter et chargement des informations de construction dans CQD, comme décrit dans la section suivante.

**Pour importer les modèles (. CQDX) en CQD en ligne**

1.  Accédez à <https://cqd.lync.com>.

2.  Authentification à l’aide de vos informations d’identification d’administration Office 365.

> [!NOTE]
> Vous devez disposer d’Office 365 administrateur Global, Skype pour l’administrateur d’entreprise ou rôle lecteurs de rapports accéder aux CQD. 


3.  Sélectionnez le menu de **Rapports de synthèse** dans la partie supérieure de la page, puis choisissez **Des rapports détaillés**.

4.  Dans le volet Résumé, sélectionnez **Importer**. Accédez à la CQDX enregistré emplacement, sélectionnez le modèle CQDX et sélectionnez **Ouvrir**.

5.  Une fois que le modèle est téléchargé, une fenêtre indépendante affiche le message « rapport importation a réussi. » Sélectionnez **OK.**

![Capture d’écran d’une fenêtre contextuelle qui informe l’utilisateur que le modèle a été correctement importé.](media/quality-of-experience-review-guide-imagestep5.png)

6.  Répétez les étapes 4 et 5 pour le deuxième modèle CQD.

> [!NOTE]
> Importer les modèles CQD par utilisateur. Si d’autres utilisateurs doivent utiliser le rapport, ils doivent se connecter et importer les modèles dans leur instance CQD. 


## <a name="building-mapping"></a>Mappage de construction

Dans un équipes ou Skype pour le déploiement d’entreprise en ligne, tous les clients externes.
Qui a les conséquences que par défaut, tous les clients sont signalés comme à l’extérieur dans CQD en ligne, quel que soit si le client est connecté sur un réseau d’entreprise interne.

Lorsque vous travaillez avec la qualité des appels, vous devez connaître l’emplacement d’un client et si elle était connecté à un réseau ou un réseau, vous pouvez gérer les vous ne pouvez pas gérer — l’hypothèse en cours que vous pouvez améliorer les réseaux seulement vous pouvez gérer.
En téléchargeant le réseau et les informations de construction sur CQD en ligne, vous activez CQD déterminer si un client a été connecté à un réseau d’entreprise/gérées interne ou à un réseau externe/non.

### <a name="building-data-file-structure"></a>Structure de fichier de données de création

Le format du fichier de données que vous téléchargez doit respecter les conditions suivantes pour transmettre le contrôle de validation avant le téléchargement.

-   Le fichier doit être un fichier TSV, ce qui signifie que, pour chaque ligne, chaque colonne est séparée par un caractère de tabulation, ou un fichier CSV dans lequel chaque colonne est séparée par une virgule.

-   Le fichier ne peut pas être supérieur à 50 Mo.

-   Le contenu des données du fichier *ne doit pas inclure les en-têtes de tableau*. En d’autres termes, la première ligne du fichier de données doit correspondre à des données réelles, pas les en-têtes de colonne tels que « Réseau ».

-   Pour chaque colonne, le type de données peut uniquement être Bool, nombre ou chaîne. Si le type de données est un nombre, la valeur doit être une valeur numérique ; s’il est Bool, la valeur doit être 0 ou 1.

-   Pour chaque colonne, si le type de données est la chaîne, les données ne peuvent être vides (mais doivent toujours être séparées par un séparateur approprié, qui est un caractère de tabulation ou une virgule). Cela affecte uniquement ce champ une valeur de chaîne vide.

-   Il doit être 14 colonnes pour chaque ligne. Chaque colonne doit avoir le type de données décrit dans le tableau suivant, et les colonnes doivent être dans l’ordre indiqué dans le tableau.

_Tableau 5 : création de structure de fichier_

| Nom de la colonne        | Type de données | Exemple                   | Conseils    |
|--------------------|-----------|---------------------------|-------------|
| Réseau            | Chaîne    | 192.168.1.0               | Obligatoire    |
| Nom_réseau        | Chaîne    | États-Unis/Seattle/SEATTLE-marin-1 | Obligatoire\*  |
| NetworkRange       | Numéro    | 26                        | Obligatoire    |
| BuildingName       | Chaîne    | SEATTLE-MARIN-1             | Obligatoire\*  |
| OwnershipType      | Chaîne    | Contoso                   | Facultatif    |
| BuildingType       | Chaîne    | Arrêt de l’informatique            | Facultatif    |
| BuildingOfficeType | Chaîne    | Ingénierie               | Facultatif    |
| Ville               | Chaîne    | Seattle                   | Recommandation |
| Code postal            | Chaîne    | 98001                     | Recommandation |
| Pays            | Chaîne    | NOUS                        | Recommandation |
| État              | Chaîne    | WA                        | Recommandation |
| Région             | Chaîne    | MSUS                      | Recommandation |
| InsideCorp         | Bool      | 1                         | Obligatoire    |
| ExpressRoute       | Bool      | 0                         | Obligatoire    |

\*Alors que ne pas requis par CQD, les modèles sont configurés pour afficher la génération et réseau nom.

#### <a name="supernetting"></a>Création de super-réseaux

Vous pouvez utiliser super-réseaux, généralement appelé inter-Domain Routing (CIDR), à la place de définition de chaque sous-réseau. Un *supernet* est une combinaison de plusieurs sous-réseaux qui partagent un préfixe de routage unique. Au lieu de l’ajout d’une entrée pour chaque sous-réseau, vous pouvez utiliser l’adresse super-réseaux/CIDR. Super-réseaux est pris en charge, mais nous ne recommandons pas l’utiliser.

Par exemple, construction marketing de Contoso est composée des sous-réseaux ci-dessous :

-   10.1.0.0/24 – premier étage

-   10.1.1.0/24 – deuxième étage

-   10.1.2.0/24 – troisième étage

-   10.1.3.0/24 – quatrième floor

Au lieu de l’ajout d’une entrée pour chaque sous-réseau, vous pouvez utiliser l’adresse super-réseaux/CIDR — dans cet exemple, 10.1.0.0/22.

-   Réseau = 10.1.0.0

-   Plage réseau = 22

Voici quelques points à prendre en compte avant d’implémenter super-réseaux :

-   Super-réseaux nécessite moins de temps en amont, mais il s’agit au détriment de la réduction de la plus grande richesse de vos données. Supposons qu’il existe un problème de qualité impliquant sous-réseau 200.1.2.0. Si vous implémenté super-réseaux, vous ne savez où se trouve le sous-réseau dans le bâtiment ou le type de réseau est (par exemple, un laboratoire). Si vous avez défini tous les sous-réseaux d’un bâtiment et télécharger des informations d’emplacement floor, vous ne pourrez pas voir cette distinction.

-   Il est important de s’assurer que l’adresse super-réseaux/CIDR est correct et qu’il n’est pas intercepter les sous-réseaux.

-   Super-réseaux peut être utilisée dans un mappage de construction avec masque de bits 28 8 bits.

-   Il est fréquent de rechercher 192.168.0.0 dans les données. Pour de nombreuses organisations, cela indique que l’utilisateur est à domicile. Pour d’autres personnes, il s’agit d’un schéma d’adresse IP pour une succursale. Si votre organisation a des bureaux qui utilisent cette configuration, ne pas inclure dans votre fichier de construction comme il est difficile de faire la distinction entre les réseaux internes et personnel à l’aide de sous-réseaux courantes.

> [!IMPORTANT]
> La plage réseau peut être utilisée pour représenter un supernet. Création de toutes les nouvelles données les téléchargements de fichiers qui est vérifié pour toutes les plages qui se chevauchent. Si vous avez déjà chargé un fichier de construction, téléchargez le fichier en cours et télécharger à nouveau pour identifier les chevauchements et corriger le problème. Les mappages incorrectes de sous-réseaux aux bâtiments dans les rapports pouvant entraîner un chevauchement des fichiers téléchargés précédemment. 


#### <a name="vpn"></a>VPN

Les données de qualité de l’expérience (QoE) qui envoient des clients à Office 365, qui est où sont issues des données CQD — inclut un indicateur VPN. Toutefois, cet indicateur s’appuie sur fournisseurs VPN reporting Windows que la carte du réseau VPN enregistrée est une carte d’accès à distance. Pas de tous les fournisseurs VPN enregistrement correctement les cartes d’accès à distance. Pour cette raison, vous pourrez pas utiliser les filtres de requête VPN intégrés. Il existe deux approches pour les sous-réseaux de réseau privé virtuel dans la création de fichier d’informations.

-   Définir un **Nom de réseau** en utilisant le texte « VPN » dans ce champ pour les sous-réseaux de réseau privé virtuel.

![Capture d’écran d’un rapport du tableau de bord de la qualité des appels qui définit la création d’un sous-réseau de réseau privé virtuel](media/quality-of-experience-review-guide-image10.png)

_La figure 10 - VPN à l’aide du nom de réseau_

-   Définir le **Nom de la construction** en utilisant le texte « VPN » dans ce champ pour les sous-réseaux de réseau privé virtuel.

![Capture d’écran d’un rapport du tableau de bord de la qualité des appels qui détermine comment créer une définition de construction qui comprend un sous-réseau de réseau privé virtuel.](media/quality-of-experience-review-guide-image11.png)

_La figure 11 - VPN à l’aide du nom de la construction_

> [!IMPORTANT]
> Certaines implémentations VPN ne signalent correctement les informations de sous-réseau. Si cela se produit dans votre rapport, qu'il est recommandé que lorsque vous ajoutez un sous-réseau de réseau privé virtuel à la création du fichier, au lieu d’une entrée pour le sous-réseau, ajoutez des entrées pour chaque adresse du sous-réseau de réseau privé virtuel comme un réseau distinct de 32 bits. Chaque ligne peut avoir les mêmes métadonnées de construction. Par exemple, au lieu d’une ligne pour 172.16.18.0/24, vous avez 253 lignes, avec une ligne pour chaque adresse de 172.16.18.1/32 par le biais de 172.16.18.254/32, inclus.


> [!NOTE]
> Les connexions VPN ont été identifiées mal identifier la connexion réseau comme filaire lorsque la connexion internet sous-jacent est sans fil. Lors de la recherche au niveau de qualité sur les connexions VPN, vous ne pouvez pas supposer que le type de connexion a été correctement identifié.

### <a name="uploading-building-information"></a>Chargement des informations de création

Le tableau de bord des rapports de synthèse CQD comprend une page **De téléchargement de données client** , accédée en sélectionnant la balise de lien **De téléchargement de données client** dans le coin supérieur droit (recherchez l’icône représentant un engrenage). Cette page est utilisée pour les administrateurs à télécharger leurs propres informations, telles que le mappage de l’adresse IP et les informations géographiques, mappage de chaque point d’accès sans fil et son adresse MAC et ainsi de suite.

1.  Accédez à CQD en ligne en accédant à <https://cqd.lync.com>.

2.  Sélectionnez l’icône représentant un engrenage dans le coin supérieur droit et choisissez **De téléchargement de données client** dans la page **Rapports de synthèse** .

![Capture d’écran d’une boîte de dialogue appels qualité du tableau de bord qui s’affiche lors du téléchargement de données.](media/quality-of-experience-review-guide-image12.png)

_La figure 12 - menu du téléchargement des données client_

1.  Autrement, s’il s’agit de votre première visite CQD, vous devez télécharger les données de création. Vous pouvez sélectionner **Télécharger** pour accéder rapidement à la page **De téléchargement de données client** .

![Capture d’écran d’une bannière du tableau de bord de qualité des appels qui signale un utilisateur de télécharger des données de création.](media/quality-of-experience-review-guide-image13.png)

_Figure 13 : création de bannière de téléchargement de données_

1.  Dans la page **De téléchargement de données client** , sélectionnez **Parcourir** pour choisir un fichier de données.

2.  Après avoir sélectionné un fichier de données, spécifiez la **date de début** et, le cas échéant, spécifiez une date de fin.

3.  Après avoir sélectionné la **date de début**, sélectionnez **Télécharger** pour télécharger le fichier à la CQD. <br><br>Avant que le fichier est téléchargé, il est validé. Si la validation échoue, un message d’erreur s’affiche demandant de corriger le fichier. La figure suivante illustre une erreur ne se produise lorsque le nombre de colonnes dans le fichier de données est incorrect.

![Capture d’écran d’une boîte de dialogue du tableau de bord de la qualité des appels qui décrit un message d’erreur lors de l’importation de données de création.](media/quality-of-experience-review-guide-image14.png)

_Figure 14 : erreur de chargement de données de création_

4.  Si aucune erreur ne se produire lors de la validation, le téléchargement du fichier réussit. Vous pouvez voir le fichier de données téléchargées dans la table **Mes téléchargements** , qui affiche la liste complète de tous les fichiers téléchargés pour le client au bas de la page actuels.

> [!NOTE]
> Cela peut prendre jusqu'à quatre heures pour terminer la création du fichier de traitement. <br><br> Si vous avez téléchargé un fichier de construction et pour ajouter les sous-réseaux qui peuvent avoir manquées ou exclus, modifier le fichier d’origine en ajoutant les nouveaux sous-réseaux, supprimez le fichier actuel et téléchargez de nouveau le fichier nouvellement modifié. Il peut y avoir qu’une construction active CQD fichier de données. 

### <a name="missing-subnets"></a>Sous-réseaux manquants

Après avoir téléchargé les informations de construction de réseaux gérés, tous les réseaux géré doivent avoir une association de construction. Toutefois, ce n’est pas toujours le cas ; en règle générale, plusieurs sous-réseaux sont ignorés. Cette section explique comment valider les réseaux manquant.

Accédez à la page **Des rapports détaillés** dans CQD en ligne et accédez au **Rapport de sous-réseau manquant** inclus dans les modèles CQD. Cela présente tous les sous-réseaux avec des flux de 10 ou plus audio qui ne sont pas définis dans la création du fichier de données. Assurez-vous qu’il n’y a aucun réseaux gérés dans cette liste. S’il manque des sous-réseaux, mettre à jour la construction d’origine du fichier de données et téléchargement de nouveau à CQD.

> [!IMPORTANT]
> Vous devez ajouter votre ID de client comme un filtre de requête pour le **Second ID client** à ce rapport pour filtrer le rapport pour afficher uniquement les données client de votre organisation. Dans le cas contraire, l’état affiche les sous-réseaux fédérés.

> [!NOTE] 
> Veillez à régler le filtre de rapport mois année au mois actuel. Sélectionnez **Modifier**, puis ajustez le filtre de rapport **Mois année** pour enregistrer le nouveau mois par défaut.                                                  |

![Rapport montrant les sous-réseaux non inclus dans le fichier de données de création de CQD qui illustrent l’utilisation.](media/quality-of-experience-review-guide-image15.png)

_Figure 15 : manquante Création état_

## <a name="reliability-investigations"></a>Enquêtes de fiabilité

Pour améliorer la qualité de la première étape consiste à évaluer l’état de fiabilité audio dans l’organisation. Étant donné que la fiabilité audio est vitale pour une expérience utilisateur positive, nous commençons par les deux composants qui mesurent la fiabilité :

1.  **Appeler les échecs d’installation :** Session n’a pas pu être établie.

2.  **Appeler les échecs de dépôt :** Session a été établie et de manière inattendue

Dans cette section, nous allons couvre les méthodes étudier les deux domaines.

> [!NOTE]
> Pas tous les rapports inclus dans les modèles sont abordées dans ce guide. Reportez-vous à la description du rapport individuels pour plus d’informations.


### <a name="call-setup"></a>Configuration des appels

Définir la priorité des erreurs appel appropriées dans ce domaine tout d’abord, car ces défaillances ont un impact négatif sur l’expérience utilisateur.

Commencer votre enquête en évaluant le pourcentage d’échecs d’installation appel globale pour l’organisation, puis définir la priorité des zones d’enquête en fonction du pourcentage de la plus élevé par bâtiment ou réseau.

#### <a name="call-setup-failures-overall"></a>Échecs d’installation globales des appels

Ce rapport de graphique affiche la quantité totale d’appel réussi, configurer et appelez des échecs d’installation au fil du temps. Pointez sur l’une des colonnes pour afficher ses valeurs spécifiques, comme le montre la figure ci-dessous.

![Capture d’écran d’un graphique qui indique le pourcentage d’échec du programme d’installation flux des appels Audio](media/quality-of-experience-review-guide-image16.png)

_Échecs d’installation de la figure 16 - fiabilité Audio - appel flux_

##### <a name="analysis"></a>Analyse

Ce rapport affiche l’utilisation du programme d’installation d’appel audio de votre organisation et des échecs au fil du temps. À l’aide de ce rapport, vous pouvez répondre aux questions suivantes et déterminez votre plan d’action suivant :

1.  Quel est le pourcentage d’échec total d’appel du programme d’installation pour le mois en cours ?

2.  Est le pourcentage d’échec du programme d’installation appel total inférieure ou supérieure à la mesure cible définie ?

3.  Est la tendance à l’échec pire supérieures ou égales du mois précédent ?

4.  La tendance à l’échec augmente, steady, ou diminue ?

Les informations présentées dans ce rapport indiquera l’histoire de la fréquence à laquelle vos configurations appel global ne sont pas au sein de votre organisation.

Indépendamment des réponses précédentes, prenez le temps d’étudier la question davantage à l’aide de rapports secondaire inclus Rechercher tout individuelles ou des réseaux qui peuvent nécessiter des mesures correctives. Bien que le taux d’échec global sous la mesure cible, souvent le taux d’échec d’un ou plusieurs bâtiments ou réseaux est au-dessus de la mesure et correction de besoin.

#### <a name="call-setup-failures-by-building-and-subnet"></a>Appeler des échecs d’installation en créant et en sous-réseau 

Ce rapport de tableau est utilisé pour détecter et isoler des bâtiments ou des réseaux nécessitant une correction.

> [!NOTE]
> Veillez à régler le filtre de rapport mois année au mois actuel. Sélectionnez **Modifier**, puis ajustez le filtre de rapport **Mois année** pour enregistrer le nouveau mois par défaut.


![Signaler que listes appel des raisons de défaillance du programme d’installation, organisées par la création, le réseau et sous-réseau par mois.](media/quality-of-experience-review-guide-image17.png)

_Figure 17 : échecs de configuration Audio en créant ou le sous-réseau_

##### <a name="remediation"></a>Mise à jour 

Ciblez vos efforts de correction de bâtiments ou les sous-réseaux qui ont le plus grand volume d’échecs tout d’abord, car cela permet de réduire rapidement les échecs d’installation d’organisation d’appel et optimiser l’impact sur l’expérience utilisateur.
Le tableau suivant répertorie les deux raisons pour les échecs d’appel du programme d’installation, comme indiqué par CQD.

_Le tableau 6 – raisons pour le programme d’installation d’échecs d’appel_

| Appelez la raison d’échecs d’installation                       | Causes courantes                                                                                                                                                                                                                                                                                   |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Règle d’Exemption Inspection manquant TR approfondie des paquets | Indique qu’équipement réseau ainsi que le chemin d’accès interdit le chemin d’accès des médias établie en raison des règles d’inspection approfondie des paquets. Il s’agit probablement en raison de règles de pare-feu n’est pas configurés correctement. Dans ce cas la négociation TCP a réussi, mais la négociation de SSL n’est pas.               |
| Manque de règle d’Exception de pare-feu IP bloc               | Indique qu’équipement réseau ainsi que le chemin d’accès interdit le chemin d’accès des médias est établie avec le réseau d’Office 365. Cela peut être en raison des règles de proxy ou un pare-feu n’est pas correctement configurés pour autoriser l’accès à des adresses IP et les ports utilisés pour les équipes et Skype pour le trafic d’entreprise. |

Maintenant que vous commencez votre mise à jour, vous pouvez vous concentrer vos efforts sur une construction spécifique ou un sous-réseau. Comme le montre le tableau précédent, ces problèmes sont en raison de configurations de pare-feu ou proxy. Passez en revue les options dans le tableau suivant pour les actions de mise à jour.

_Le tableau 7 - étapes suivantes pour l’appel du programme d’installation de la correction d’erreur_

| Mise à jour           | Conseils     |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configurer l’ou les pare-feu | Travailler avec votre équipe réseau et vérifiez votre configuration ou les pare-feu par rapport à [la liste d’adresses IP de Office 365](https://aka.ms/o365ips). Vérifiez que les ports et les [sous-réseaux multimédia](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) sont inclus dans les règles de pare-feu. Vérifiez que les ports TCP et UDP nécessaires sont ouverts dans le pare-feu. Media préfère UDP sur TCP. TCP est considéré comme un protocole de la restauration automatique.<br><ul><li>**TCP :** le port 443</li><li>**UDP :** ports – 3481 3478</li><ul> |
| Vérifier                | Tirer parti de l' [Outil d’évaluation de réseau Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) pour vérifier la connectivité à partir du bâtiment concerné ou d’un sous-réseau à l’aide de la fonction de vérification de connectivité.    |


### <a name="call-drop"></a>Liste des appels

Contrairement aux échecs d’appel du programme d’installation, il est aucun code motif pour indiquer pourquoi appel abandonné échecs s’est produite, qui rend difficile à isoler une cause spécifique. Pour mieux triage appels abandonnés, utilisez une approche déduite. Par corriger les zones d’intérêt pour l’audio, mise à jour des clients et pour l’utilisation de périphériques certifiés pour les équipes et Skype pour les entreprises, vous attendriez d’échecs d’appel rejeté pour refuser.

#### <a name="call-drop-failures-overall"></a>Échecs de dépôt globale des appels

Ce rapport graphique affiche le montant total des flux audio, des flux audio total supprimées, et les flux total supprimé pourcentage. Pointez sur l’une des colonnes pour afficher ses valeurs, comme le montre la figure suivante.

![Capture d’écran d’un graphique illustrant le pourcentage de supprimé de flux des appels Audio](media/quality-of-experience-review-guide-image18.png)

_Pourcentage d’échec de la figure 18 - appel Total supprimée_

##### <a name="analysis"></a>Analyse

Ce rapport graphique affiche l’utilisation de votre organisation et des échecs au fil du temps relatives aux appels projections. À l’aide de ce rapport, vous pouvez répondre aux questions suivantes :

1.  Quel est l’appel en cours total supprimé pourcentage ?

2.  Est le pourcentage du total de dépôt sous la mesure cible définie ?

3.  Est la tendance à l’échec pire supérieures ou égales du mois précédent ?

4.  La tendance à l’échec augmente, steady, ou diminue ?

Les informations présentées dans ce rapport peuvent indiquer l’article de la fréquence à laquelle votre projections appel globale sont produisent au sein de votre organisation.

Indépendamment des réponses aux questions ci-dessus, prenez le temps d’étudier la question à l’aide de rapports secondaire pour rechercher des réseaux qui peuvent nécessiter des mesures correctives ni de bâtiments. Bien que le taux de dépôt global sous la mesure cible, souvent le taux de dépôt pour un ou plusieurs bâtiments ou réseaux au-dessus de la mesure et doit correction.

#### <a name="call-drop-failures-by-building-or-subnet"></a>Appeler des échecs de dépôt en création ou le sous-réseau

Échecs dans ce rapport de tableau indiquent que l’appel a été supprimé de manière inattendue et a provoqué une expérience utilisateur négatif. Il existe deux rapports de tableau inclus dans le modèle, un pour l’examen de conférence et l’autre pour les deux.

> [!NOTE]
> Veillez à régler le filtre mois année au mois actuel. Sélectionnez **Modifier**, puis ajuster les **Mois année** pour enregistrer le nouveau mois par défaut.


![Rapport qui répertorie le nombre et le pourcentage de supprimé des appels, organisées par la création, le réseau et sous-réseau par mois.](media/quality-of-experience-review-guide-image19.png)

_La figure 19 – appel Audio supprimée échecs par bâtiment ou le sous-réseau_

##### <a name="remediation"></a>Mise à jour

À l’aide du rapport de tableau précédent, vous pouvez désormais isoler les « points sensibles » dans le réseau géré où projections d’appel sont supérieures à la mesure cible définie. Ciblez vos efforts de correction de bâtiments ou des réseaux dont le nombre total de flux de données la plus élevé tout d’abord, pour avoir un impact considérable.

Causes courantes des projections d’appel :

-   Sous-mis en service réseau ou internet sortant

-   Aucun QoS configuré sur les réseaux de contraintes

-   Versions antérieures du client

-   Comportement de l’utilisateur

Une fois que vous détectez des points d’accès, vous pouvez exploiter [Analytique d’appel](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309) pour les utilisateurs de la création des problèmes spécifiques un examen plus approfondi. Appel Analytique contient des données personnelles et peut être utile pour isoler davantage les raisons pour l’appel projections.

Quel que soit l’étape suivante, il est conseillé d’avertir le support technique qu’un problème a été détecté avec bâtiments spécifiques ou les sous-réseaux. De cette manière, ils peuvent rapidement répondre aux appels entrants et trier les utilisateurs plus efficacement. Les utilisateurs avec indicateur peuvent ensuite être renvoyées à l’équipe d’ingénierie examinés.

Le tableau suivant répertorie certaines méthodes courantes pour gérer et résoudre les projections d’appel.

_Le tableau 9 - étapes suivantes pour l’appel drop correction_

| Mise à jour                              | Conseils     |
|------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Réseau à internet                         | Maintenant que vous savez quelle construction est affectée, travailler avec votre équipe réseau pour surveiller la bande passante à cette construction afin de déterminer s’il existe des problèmes liés à l’utilisation abusive. Si le problème est détecté doit être associée à une surcharge réseau, tenez compte des augmenter la bande passante pour cette création. <br><br>**QoS :** Si l’augmentation de la bande passante est impossible ou envisageable, envisagez l’implémentation de QoS. Ceci garantit des paquets de médias sur le réseau géré sont hiérarchisés au-dessus du trafic non multimédia. Ou bien, s’il n’existe aucune clairement que la bande passante est défaillant, prenez en compte ces solutions :<br><ul><li>[Conseils de QoS équipes Microsoft](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)</li><li>[Skype pour obtenir des instructions Business QoS](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul><br>**Effectuer une évaluation de préparation du réseau :** Une évaluation réseau fournit des détails sur l’utilisation de la bande passante attendue, comment faire face à la bande passante et réseau change, réseau pratiques recommandées pour les équipes et Skype pour les entreprises. À l’aide du tableau précédent comme source, vous disposez d’une liste de bâtiments ou les sous-réseaux qui sont une excellente candidats pour une évaluation. <br><ul><li>[Évaluation de préparation du réseau équipes Microsoft](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#test-the-network)</li><li>[Skype pour l’évaluation de préparation du réseau Business](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Outil d’évaluation de Microsoft Network :** Utilisez cet outil pour un simple test des performances du réseau pour déterminer comment exécuter le réseau pour une équipes ou Skype pour les appels professionnels en ligne. L’outil vous permet d’évaluer les performances d’un sous-réseau et valider la préparation du réseau par rapport à des [exigences](https://aka.ms/performancerequirements)de performances Microsoft.<ul><li>[Télécharger l’outil d’évaluation réseau](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul>         |
| Clients (Skype pour les entreprises en ligne uniquement) | Certains clients antérieurs ont connu, documentée problèmes avec la fiabilité des supports. Examinez les rapports Analytique appeler à partir de plusieurs utilisateurs affectés ou créer un rapport de tableau de Version du Client personnalisé dans CQD filtré bâtiments spécifiques ou les sous-réseaux avec mesure de % échec Total appel rejeté. Ces informations vous aideront à comprendre l’existence d’une relation entre projections d’appel dans un bâtiment en particulier et une version spécifique du client.                                                                                                                                                              |
| Périphériques                                  | La plupart des échecs de périphériques sont en raison de l’utilisation de périphériques non certifiés pour les équipes ou Skype pour les entreprises. Échecs prennent généralement la forme haut-parleurs intégrés ou micros sont utilisées, ou les combinaisons d’écouteur/micro qui sont connectés à la prise audio 3,5 mm sur un appareil. Recommandation actuelle de Microsoft est que tous les utilisateurs qui rencontrent appellent projections — ou médiocres appelle en général et sont à l’aide de périphériques intégrées ou pilotes doit être mis en service un [certifié casque ou téléphone mains libres](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). |
| Comportement de l’utilisateur                            | Si vous avez déterminé que ni réseau, des périphériques ou des clients sont le problème, envisagez d’engager [Mon Advisor](https://aka.ms/myadvisor) pour obtenir des conseils dans le développement d’une stratégie utilisateur d’adoption apprendre aux utilisateurs comment meilleures joindre et quitter des réunions. Un équipes intelligente et Skype utilisateur produira une meilleure expérience utilisateur pour tous les participants à la réunion. Un utilisateur qui met leur ordinateur portable en mode veille (à la fermeture du capot) sans quitter la réunion est considéré comme une liste d’appel inattendu.     |

## <a name="quality-investigations"></a>Enquêtes de qualité

L’étape suivante pour évaluer l’état de la qualité audio lors du déploiement consiste à étudier Audio médiocre appeler taux (PCR), TCP et l’utilisation du proxy. Il est important de noter que les données CQD ne fournissent une cause spécifique, mais vous propose des problèmes susceptibles de commencer une conversation collaboration avec les équipes appropriés pour les activités de mise à jour au lieu de cela.

> [!NOTE]
> Pas tous les rapports inclus dans les modèles sont abordées dans ce guide. Reportez-vous à la description du rapport individuels pour plus d’informations. 


### <a name="investigate-call-quality"></a>Examiner la qualité des appels

Le pourcentage PCR global est principalement utilisé pour indiquer si l’organisation est objectifs définis audio métrique. Il est important de noter que même si le pourcentage global de cible, certains sous-réseaux ou bâtiments ne peut-être pas atteindre les objectifs définis et donc approfondir. Par exemple, si le pourcentage PCR audio d’organisation 3 pour cent dans décembre, qui répond à la cible de l’exemple, bâtiments spécifiques peut toujours avoir une mauvaise expérience, en fonction de la distribution de ce % 3.

#### <a name="overall-organizational-poor-call-percentage"></a>Pourcentage d’appels médiocres d’organisation de global

Pour évaluer le pourcentage d’appels médiocres pour l’organisation global utiliser le rapport de graphique qualité globale.

![Capture d’écran d’un graphique illustrant le pourcentage d’appels de qualité médiocre](media/quality-of-experience-review-guide-image20.png)

_La figure 20 – qualité Audio - général_

##### <a name="investigation"></a>Enquête

Ce rapport graphique affiche d’utilisation de votre organisation et PCR au fil du temps. À l’aide de ce rapport, vous pouvez répondre aux questions suivantes :

1.  Quel est la total PCR pour le mois en cours ?

2.  Voici la PCR la mesure cible définie ?

3.  Est la tendance à l’échec pire supérieures ou égales du mois précédent ?

4.  La tendance à l’échec augmente, steady, ou diminue ?

Indépendamment des réponses aux questions ci-dessus, prenez le temps d’étudier la question en utilisant les rapports secondaire pour rechercher des réseaux qui peuvent nécessiter plus enquête ni de bâtiments. Bien que la PCR globale sous la mesure cible, souvent PCR pour un ou plusieurs bâtiments ou réseaux au-dessus de la mesure et doit davantage enquête.

#### <a name="audio-quality-overall"></a>Qualité audio globale

Il existe deux arborescences de rapport inclus dans les modèles de qualité audio, l’autre pour l’analyse de conférence et l’autre pour les appels à deux. Pour les besoins de correction de la qualité, le processus d’enquête étant identiques, nous nous concentrerons ici sur la conférence. Améliorations de la qualité de conférence affecte également positive la qualité des appels de deux. Les rapports sont également inclus pour afficher une qualité audio pour la conférence et deux par filaire et Wi-Fi.

> [!NOTE]
> Examen aux appels à une mauvaise deux est similaire à l’analyse des téléconférences. La tâche consiste à identifier les bâtiments ou les sous-réseaux dont la qualité de la plus faible à valider s’il existe un modèle d’appels médiocres avec un autre bâtiment ou le sous-réseau. 

![Capture d’écran de la qualité Audio - état de conférence dans le tableau de bord qualité des appels.](media/quality-of-experience-review-guide-image21.png)

_La figure 21 – qualité Audio - conférence_

##### <a name="investigation"></a>Enquête

Ce rapport de graphique affiche la conférence de votre organisation ou d’utilisation de deux et PCR au fil du temps. À l’aide de ce rapport, vous pouvez répondre aux questions suivantes :

1.  Quel est la total PCR pour le mois en cours ?

2.  Voici la PCR la mesure cible définie ?

3.  Est PCR pire supérieures ou égales du mois précédent ?

4.  La tendance PCR augmente, steady, ou diminue ?

Indépendamment des réponses aux questions ci-dessus, prenez le temps d’étudier la question en utilisant les rapports secondaire pour rechercher les bâtiments ou les réseaux qui peuvent nécessiter l’enquête. Bien que la PCR globale sous la mesure cible, souvent PCR pour un ou plusieurs bâtiments ou réseaux au-dessus de la mesure et doit correction.

#### <a name="poor-audio-stream-by-building-and-subnet"></a>Flux audio médiocre en créant et en sous-réseau

Ce rapport de tableau vous donne des informations supplémentaires sur ce qui a contribué à appels en cours classé comme médiocre et aide à identifier les points faibles du réseau géré.

Fait la distinction entre les informations de connexion filaire et Wi-Fi et inclut la gigue, la perte de paquets et les mesures de temps d’aller-retour (durée aller-retour). Un rapport similaire existe sous deux rapports et est utilisé pour isoler les appels à deux sur votre réseau géré.

> [!NOTE]
> Veillez à régler le filtre mois année au mois actuel. Sélectionnez **Modifier**, puis ajuster les **Mois année** pour enregistrer le nouveau mois par défaut. 

> [!TIP]
> Réseaux domestiques courantes sont difficiles à triage en raison de leur utilisation généralisée. Un rapport distinct qui utilise l’adresse IP du pare-feu a été ajouté au modèle de tous les réseaux pour vous aider à la correction des bureaux qui utilisent des réseaux.

![Rapport qui répertorie les types de connexion, les types de transport et PCR supérieure à 3 % ainsi que les différents motifs de qualité médiocre, organisées par la création, le réseau et sous-réseau par mois.](media/quality-of-experience-review-guide-image22.png)

_La figure 22 - résumé en créant des flux Audio médiocre - et sous-réseau conférence_

##### <a name="remediation"></a>Mise à jour

Concentrer vos efforts de correction de bâtiments ou rencontrent rapidement des réseaux qui ont le plus grand volume de flux audio, car cela optimiser impact et contribuer à l’amélioration de l’utilisateur. Utilisez la gigue, la perte de paquets et les mesures de durée aller-retour pour comprendre ce qui contribue à la qualité des appels médiocres. Il est possible d’avoir plusieurs problèmes :

-   **Gigue :** Paquets de médias sont reçus par différentes vitesses, ce qui provoque un haut-parleur pour son automatisée.

-   **La perte de paquets :** Paquets de médias sont en cours de suppression, qui crée l’effet de mots ou des syllabes manquants.

-   **Durée aller-retour :** Paquets de médias sont prend beaucoup de temps pour accéder à leur destination, qui crée un effet talkie-walkie.

Bien qu’aucune source unique de la véracité des comptes pour ce qui peut provoquer un appel médiocre, plusieurs méthodes courantes peuvent vous aider à relever concernant les anomalies réseau.

Pour aider votre enquête sur les problèmes de qualité, vous pouvez exploiter [Analytique d’appel](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309).
Avec l’appel Analytique, vous pouvez examiner une conférence spécifique ou un état d’appel détaillées des utilisateurs. Ce rapport contient les données d’identification personnelle et est utile lorsque vous tentez d’identifier un motif d’échecs. Une fois que vous connaissez les création qui est affecté, le suivi des utilisateurs vers le bas dans cette construction doit être simple.

N’oubliez pas d’informer le service d’assistance que ces réseaux rencontrent des problèmes de qualité, afin qu’ils puissent rapidement triage et répondre aux appels entrants.

_Le tableau 9 - courantes collaborateurs à haute PCR_

| Mise à jour                              | Conseils       |
|------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Réseaux                                 | Un utilisation excessive ou configurées sous réseau peut entraîner des problèmes avec la qualité des médias. Travail avec l’équipe réseau pour déterminer si les connexions réseau à partir de l’utilisateur à la sortie internet point a suffisamment de bande passante pour prendre en charge multimédia. **Effectuer une évaluation de préparation du réseau :** Une évaluation réseau fournit des détails sur l’utilisation de la bande passante attendue, comment faire face à la bande passante et réseau change, réseau pratiques recommandées pour les équipes et Skype pour les entreprises. À l’aide du tableau précédent comme source, vous disposez d’une liste de bâtiments ou les sous-réseaux qui sont une excellente candidats pour une évaluation.<br><ul><li>[Évaluation de préparation du réseau équipes Microsoft](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#test-the-network)</li><li>[Skype pour l’évaluation de préparation du réseau Business](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Outil d’évaluation de Microsoft Network :** Utilisez cet outil pour un simple test des performances du réseau pour déterminer comment exécuter le réseau pour une équipes ou Skype pour les appels professionnels en ligne. Cet outil vous permet d’évaluer les performances d’un sous-réseau et valider la préparation du réseau par rapport à Microsoft performance [requirements](https://aka.ms/performancerequirements).<br><ul><li>[Télécharger l’outil d’évaluation réseau](https://www.microsoft.com/download/details.aspx?id=53885) </li></ul>        |
| Qualité de Service (QoS)                 | QoS est une méthode éprouvée pour aider à définir la priorité des paquets sur un réseau pour vous assurer qu’ils arrivent à destination intacte et sur le temps. Envisagez d’implémenter la qualité de service au sein de votre organisation afin d’optimiser la qualité de l’expérience utilisateur dans lequel la bande passante est limitée ou contrainte. QoS vous aideront à résoudre les problèmes généralement associés avec un niveau élevé de perte de paquets, et, dans une moindre mesure : temps de gigue et aller-retour. <br><ul><li>[Conseils de QoS équipes Microsoft](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)</li><li>[Skype pour obtenir des instructions Business QoS](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul>    |
| Wi-Fi                                    | Wi-Fi peut avoir un impact significatif sur la qualité des appels. Conception Wi-Fi ne généralement prend en considération la configuration réseau requise pour les services VoIP et est souvent une source de qualité médiocre. **QoS :** Les réseaux sans fil modernes doivent prendre en charge de nombreux périphériques. Ces périphériques en concurrence pour la bande passante et peuvent entraîner des problèmes de qualité pour les services VoIP où la vitesse et la latence sont essentielles. Consultez votre fournisseur sans fil pour caractéristiques et implémentez QoS sur votre réseau sans fil pour classer par priorité Skype pour professionnels et les équipes de support. **Densité AP :** Points d’accès (PA) peuvent être trop éloignés ou non dans un emplacement idéal. Pour réduire l’interférence potentielle, placez les points d’accès supplémentaires dans les salles de conférence et dans les emplacements qui ne sont pas coupés par les murs ou d’autres objets. **2,4 GHz et 5 GHz :** 5 GHz fournit moins interférences d’arrière-plan et le plus rapidement et priorité lors du déploiement VoIP en Wi-Fi. Toutefois, 5 GHz n’est pas aussi forte que 2,4 GHz et ne traversent les murs aussi facilement. Passez en revue votre mise en page de construction pour déterminer quelle fréquence dépendent de la meilleure connexion. **Force du signal :** Généralement exprimée en dBm (taux d’alimentation en décibels), cette mesure la puissance du signal sans fil. Une fois un périphérique est connecté à un point d’accès, il ne souhaite pas laisser accéder facilement. Lorsque le périphérique se trouve hors du point d’accès, le signal tombe en un point qui induit une connexion de qualité médiocre, même si le point d’accès d’une autre, plus proche est disponible. Dans la mesure du possible, contactez votre fournisseur de point d’accès pour vous assurer que les points d’accès sont configurés pour supprimer un périphérique lors de la puissance du signal inférieure à un niveau acceptable. Cela permet de garantir que le périphérique ne se bloque à un point d’accès faible. Il s’agit d’une bonne solution lorsque vous ne pouvez pas ajouter facilement plusieurs points d’accès. **Pilote sans fil :** Lorsque tout le reste échoue, vérifiez que les pilotes sans fil sont à jour. Cela permettra d’atténuer les expérience utilisateur médiocre lié à un pilote obsolète. |
| Périphérique de réseau                           | Organisations de grande taille peuvent avoir des centaines de périphériques répartis sur le réseau. Travail avec votre équipe de réseau pour vérifier les périphériques réseau à partir de l’utilisateur à internet sont gérées et à jour.     |
| VPN                                      | Il a été bien documenté que les appareils VPN ne sont pas habituellement conçus pour gérer les charges de travail de médias en temps réel. Certaines configurations VPN interdisent l’utilisation de UDP (qui est le protocole par défaut pour l’audio) et s’appuient sur TCP uniquement. Envisagez d’implémenter une [solution de fractionnement-tunnel VPN](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) pour réduire VPN en tant que source de qualité médiocre.        |
| Clients (Skype pour les entreprises en ligne uniquement) | Clients antérieurs ont été identifiés pour provoquer des problèmes de support. Assurez-vous que les clients corrigés dans les six mois de version. Tirer parti de [MyAdvisor](https://aka.ms/myadvisor) pour obtenir des instructions sur le développement d’une stratégie de préparation des clients et déployez [Click-to-Run](https://technet.microsoft.com/library/jj219427.aspx).      |
| Périphériques                                  | L’utilisation de [optimisé périphériques](https://partnersolutions.skypeforbusiness.com/solutionscatalog) peut aider à améliorer sensiblement l’expérience utilisateur. Tout ce qui est égal, périphériques optimisés sont conçus pour optimiser l’expérience utilisateur avec des équipes et Skype pour les entreprises et de qualité supérieure. Tirer parti de [MyAdvisor](https://aka.ms/myadvisor) pour obtenir des instructions sur le développement d’une stratégie de disponibilité du périphérique.   |


### <a name="investigate-tcp-audio-sessions"></a>Examiner les sessions audio TCP

TCP est considéré comme un pas le transport principal souhaité pour les médias en temps réel et la restauration automatique. Il s’agit d’un transport de la restauration automatique est en raison de la nature dynamique du protocole TCP. Par exemple, si un appel est effectué sur un réseau latent et paquets de médias sont retardées, puis les paquets d’il y a quelques secondes, qui ne sont plus utile — en concurrence pour la bande passante atteindre le récepteur, qui permet de rendre un pire situation incorrecte. Cela rend l’agrafage de réparation audio et audio étirement, entraînant des artefacts audibles souvent sous la forme de gigue.

Les rapports de cette section n’apporte une distinction entre les appels bonne et médiocres. Étant donné que UDP est préféré, les rapports de recherche pour l’utilisation de TCP pour l’audio. Cela est dû principalement par les règles de pare-feu incomplètes. Pour plus d’informations sur les règles de pare-feu pour les équipes et Skype pour Business Online, voir [Office 365 URL et plages d’adresses IP](https://aka.ms/o365ips).

> [!IMPORTANT]
> Avoir une valide de [création du fichier](#building-mapping) téléchargé est recommandé puissent rapidement distinguer à l’intérieur des flux audio extérieur lorsque vous examinez l’utilisation TCP. 


#### <a name="audio-streams-with-tcp-usage-overall"></a>Flux audio avec l’utilisation TCP globale

Ce rapport indique l’utilisation TCP globale pour l’audio sur les sept derniers mois, comme illustré ci-dessous.

Tous les autres rapports dans cette section seront concentre sur la limitation de bâtiments spécifiques et les sous-réseaux où TCP est généralement utilisée. Autres rapports secondaire décomposer l’utilisation TCP en conférence et deux appels.

![Capture d’écran d’un graphique illustrant le nombre de flux de données audio TCP par mois](media/quality-of-experience-review-guide-image23.png)

_La figure 23 – flux Audio avec l’utilisation TCP_

##### <a name="investigation"></a>Enquête

Ce rapport graphique affiche l’utilisation TCP globale de votre organisation. À l’aide de ce rapport, vous pouvez répondre aux questions suivantes :

1.  Quel est le volume total d’appels TCP pour le mois en cours ?

2.  Est-il pire supérieures ou égales du mois précédent ?

3.  Les tendances d’utilisation TCP augmente, steady, ou diminue ?

Si vous constatez que les tendances d’utilisation TCP augmente ou au-dessus d’utilisation mensuelle normale, prenez le temps d’étudier la question en utilisant les rapports secondaire pour rechercher des bâtiments ou des réseaux qui peuvent nécessiter des mesures correctives. Dans l’idéal, vous souhaitez sessions audio basés sur TCP aussi peu que possible sur le réseau géré.

#### <a name="tcp-vs-udp"></a>TCP et UDP

Ce rapport de tableau identifie le volume du protocole TCP par rapport à l’utilisation UDP création de rapports dans le mois le plus récent pour les conférences audio, vidéo et vidéo écran partage (VBSS).

![Rapport illustrant le volume du protocole TCP et flux de conférence UDP, avec PCR de comparaison](media/quality-of-experience-review-guide-image24.png)

_La figure 24 – TCP et UDP - conférence_

##### <a name="analysis"></a>Analyse

Bien que vous souhaitez que l’utilisation TCP pour être aussi faible que possible, vous pouvez voir un bit d’utilisation TCP dans un déploiement intègre dans le cas contraire. Pour comparer UDP à l’utilisation de TCP, divisez les flux audio TCP par flux audio UDP pour déterminer le pourcentage. Une valeur supérieure à 1 pour cent doit être approfondie.

Dans l’exemple ci-dessus, nous prenons 1,806 flux TCP divisés par 10,481 flux UDP d’arriver à une valeur de 17,2 %. Cette valeur est bien supérieur à 1 % et nous indique que nous devons notre enquête afin de déterminer où l’utilisation TCP est en cours.

Également inclus dans le rapport est Audio médiocre pourcentage. Cela vous donne une vue de la comparaison de la qualité des appels entre UDP et TCP pour aider à visualiser comment TCP concerne la qualité des appels overcall.

Maintenant que vous avez déterminé qu’il y a une utilisation élevée de périphérique audio que basés sur TCP dans votre organisation, que faire ensuite ? Accédez aux rapports de **flux de données TCP en créant et en sous-réseau** pour décomposer l’utilisation TCP en construction et sous-réseaux.

#### <a name="tcp-streams-by-building-and-subnet"></a>Flux de données TCP en créant et en sous-réseau

Dans les modèles CQD fournis, atteindre le flux de données TCP par sous-réseau et création de rapports de tableau à l’aide de managé ou tous les modèles de réseaux. Il existe trois états inclus dans le modèle, un pour l’examen aux conférences, avec et sans informations de relais Microsoft et l’autre pour l’examen aux deux appels. Pour les besoins de recherches sur l’utilisation TCP, le processus est la même, afin que nous nous concentrerons ici la discussion sur la conférence uniquement.

> [!IMPORTANT]
> Avoir une valide de [création du fichier](#building-mapping) téléchargé est recommandé puissent rapidement distinguer à l’intérieur des flux audio extérieur lorsque vous examinez l’utilisation TCP. 

> [!NOTE]
> Veillez à régler le filtre mois année au mois actuel. Sélectionnez **Modifier**, puis ajuster les **Mois année** pour enregistrer le nouveau mois par défaut.                                  |

![Rapport qui répertorie les flux de données TCP, organisées par la création, le réseau et sous-réseau par mois.](media/quality-of-experience-review-guide-image25.png)

_La figure 25 sous-réseau et – flux TCP en créant - conférence_

##### <a name="remediation"></a>Mise à jour

Ce rapport identifie bâtiments spécifiques et les sous-réseaux qui travaillent pour le volume de l’utilisation TCP. Un rapport supplémentaire est également inclus pour identifier l’adresse IP relais Microsoft qui a été utilisé dans l’appel pour isoler les règles de pare-feu manquant. Ciblez vos efforts de correction sur ces bâtiments dont le volume des flux audio afin d’optimiser l’impact de la plus élevé.

La cause la plus courante de l’utilisation TCP n’a pas de règles d’exception de pare-feu ou proxy. Nous parler des proxys dans la section suivante, donc pour l’instant concentrer sur les pare-feu. À l’aide de la création ou le sous-réseau fourni, vous pouvez déterminer le pare-feu doit être mis à jour.

_Tableau 10 - correction * conseils pour les flux TCP en créant et en sous-réseau_

| Mise à jour        | Conseils     |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configurer le pare-feu | Vérifier les [adresses et les ports d’Office 365 IP](https://aka.ms/o365ips) sont exclus de votre pare-feu. Bien qu’il existe plusieurs adresses IP et les ports qui doivent être ouverts pour les problèmes TCP relatifs aux médias, concentrer initiale en ce qui suit : Vérifiez les [sous-réseaux multimédia](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) suivants se trouvent dans vos règles de pare-feu. Reportez-vous à la ligne 4 dans ce tableau pour plus d’informations de sous-réseau multimédias spécifiques. [Les ports UDP 3478 – 3481](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Updated-IP-ranges-and-ports-for-Skype-for-Business-Online/ba-p/47470): ces ports sont les ports multimédias par défaut et doivent être ouvert, sinon le client est restauré sur le port TCP 443. |
| Vérifier             | Utilisez l' [Outil d’évaluation de réseau Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) pour vérifier les problèmes de connectivité à des ports et adresses Office 365 IP spécifiques à partir de la construction concernée ou le sous-réseau.    |

### <a name="investigate-http-proxy-usage"></a>Vérifiez l’utilisation du proxy HTTP

Serveurs proxy HTTP ne sont pas le chemin d’accès par défaut pour l’établissement des sessions multimédias, d’une multitude de raisons. Nombreuses contiennent des fonctionnalités d’inspection approfondie des paquets peuvent empêcher les connexions au service en cours d’exécution et présenter les interruptions de service. En outre, les proxys peuvent forcer TCP et ne pas autoriser UDP, qui est recommandée pour une qualité audio optimale.

Il est toujours recommandation de Microsoft pour configurer le client se connecte directement aux équipes et Skype pour les services. Ceci est particulièrement important pour le trafic multimédia.

> [!IMPORTANT]
> Avoir une valide de [Création de fichier](#building-mapping) téléchargé facilite la distinguer correctement à l’intérieur des flux audio externes lors de l’analyse de l’utilisation du proxy. 


#### <a name="audio-streams-with-http-proxy-usage-overall"></a>Flux audio avec l’utilisation du proxy HTTP globale

Ce rapport présente l’utilisation du proxy au fil du temps sur une échelle de tous les mois. L’état de flux de proxy HTTP dans cette section du modèle est très similaire les rapports TCP. Il ne s’affiche si les appels sont médiocres ou bon, mais si l’appel est connecté via HTTP.

![Capture d’écran des flux Audio avec le rapport d’utilisation du Proxy HTTP dans le tableau de bord qualité des appels.](media/quality-of-experience-review-guide-image26.png)

_La figure 26 – flux Audio avec l’utilisation du Proxy HTTP_

##### <a name="analysis"></a>Analyse

Si vous voyez un volume élevé d’utilisation HTTP, contactez votre équipe de mise en réseau pour assurer que les exclusions appropriées sont en place afin que les clients sont directement de routage pour les équipes ou Skype pour les sous-réseaux media Business en ligne. Dans l’idéal, il doit être sans l’utilisation HTTP affichée ici.

Si vous n'avez qu’un seul proxy internet dans votre organisation, vérifiez le bon [Office 365 URL et les exclusions de plage d’adresses IP](https://aka.ms/o365ips). Si plusieurs proxy internet est configuré dans votre organisation, utilisez le protocole HTTP sous-fonctionnalités signaler pour isoler le bâtiment ou sous-réseau est affecté.

Pour les organisations qui ne peuvent pas contourner le serveur proxy, vérifiez que le Skype pour Business client est configuré pour se connecter correctement lorsqu’il se trouve derrière un proxy comme indiqué dans l’article [Skype entreprise doit utiliser le serveur proxy pour se connecter au lieu d’essayer direct connexion](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin).

#### <a name="http-proxy-streams-by-building-and-subnet"></a>Flux de proxy HTTP en créant et en sous-réseau

Ce rapport identifie bâtiments spécifiques et les sous-réseaux à l’utilisation HTTP.

> [!IMPORTANT]
> Avoir une valide de [Création de fichier](#building-mapping) téléchargé facilite la distinguer correctement à l’intérieur des flux audio externes lors de l’analyse de l’utilisation du proxy.

> [!NOTE]
> Veillez à régler le filtre mois année au mois actuel. Sélectionnez **Modifier**, puis ajuster les **Mois année** pour enregistrer le nouveau mois par défaut.                        |

![Capture d’écran de l’utilisation du Proxy HTTP par sous-réseau et création de rapports dans le tableau de bord qualité des appels.](media/quality-of-experience-review-guide-image27.png)

_Figure 27 – utilisation de Proxy HTTP en créant et sous-réseau_

##### <a name="remediation"></a>Mise à jour

Ciblez vos efforts de correction des bâtiments ou les sous-réseaux dont l’utilisation du proxy HTTP. La cause la plus courante de l’utilisation HTTP n’a pas de règles d’exception de proxy. À l’aide de la création ou le sous-réseau fourni, vous pouvez déterminer quel proxy doit être mis à jour.

Vérifiez que le requis [Office 365 complets](https://aka.ms/o365ips) sont exclus de votre serveur proxy.

## <a name="endpoint-investigations"></a>Enquêtes de point de terminaison

Cette section se concentre sur les tâches de création de rapports de Skype pour les versions du client spécifique à l’entreprise et l’utilisation de périphériques certifiés.

> [!NOTE]
> Pas tous les rapports inclus dans les modèles sont abordées dans ce guide. Reportez-vous à la description du rapport individuels pour plus d’informations. 


### <a name="determine-client-versions"></a>Déterminer les versions du client

Le rapport dans cet espace se concentre sur l’identification Skype pour les versions de client d’entreprise en cours d’utilisation et leur volume relative dans l’environnement.

> [!IMPORTANT]
> Actuellement, les équipes clients sont distribués et mis à jour automatiquement par le biais de l’Azure réseau CDN (Content Delivery) et restent à jour par le service. Préparation des clients et activités investigation ne sont pas applicables aux équipes.

Vous pouvez trouver les numéros de version de Skype pour Business 2015 et 2016 via les liens ci-dessous :

-   [Versions de canal de mise à jour de client Office 365](https://technet.microsoft.com/office/mt465751?f=255&MSPPError=-2147217396)

-   [Numéros de version et Office 365 pour cliquer pour exécuter](https://support.office.com/article/Version-and-build-numbers-of-update-channel-releases-ae942449-1fca-4484-898b-a933ea23def7)

-   [Skype pour les entreprises télécharge et met à jour](https://technet.microsoft.com/office/dn788954.aspx)

> [!NOTE] 
> Veillez à régler le filtre mois année au mois actuel. Sélectionnez **Modifier**, puis ajuster les **Mois année** pour enregistrer le nouveau mois par défaut.  

> [!IMPORTANT]
> États clients vous obligent à exclure les données participants fédérées. Pour exclure les données participants fédérées, vous devez ajouter un filtre de requête pour **Second ID client** de votre organisation [d’ID de client](#tenant-id). |

![Capture d’écran de l’état des clients et périphériques dans le tableau de bord qualité des appels.](media/quality-of-experience-review-guide-image28.png)

_La figure 28 - état de la version de Client_

#### <a name="remediation"></a>Mise à jour

Un rôle essentiel de conduire une expérience utilisateur de qualité est de vous assurer que les clients gérés exécutant des versions à jour de Skype pour les entreprises. Cela offre plusieurs avantages, parmi lesquels :

-   Il est plus facile de gérer plusieurs versions et le nombre de versions.

-   Il fournit un niveau de cohérence de l’expérience.

-   Il est plus facile de résoudre les problèmes liés à la qualité des appels et de la convivialité.

-   Microsoft met continuellement optimisations et améliorations générales sur le produit. S’assurer que les utilisateurs reçoivent ces mises à jour permet de réduire les risques de rencontrez un problème qui a déjà été résolu.

Limitation de votre déploiement sur les versions du client qui sont moins de six mois pour améliorer l’expérience utilisateur globale et améliorer la facilité de gestion par rapport à un grand nombre de différentes versions du client dans le même environnement.

Si vous utilisez uniquement Office Click-to-Run, vous serez automatiquement pendant la période de six mois. Aucune action supplémentaire n’est requise.

If, comme la plupart des entreprises, vous disposez d’une combinaison de packages Click-to-Run et installer (MSI), vous pouvez utiliser le rapport pour vérifier que les clients MSI sont mis à jour régulièrement. Ciblez vos efforts de ces clients où le volume est supérieur à la moyenne. Si vous remarquez retard de clients, travailler avec l’équipe chargée de la gestion des mises à jour Office et vous assurer qu’ils sont l’approbation et déploiement de correctifs client régulièrement.

### <a name="devices-investigations"></a>Enquêtes de périphériques

Faire utiliser des rapports de périphérique suivants, il est recommandé de comprendre le concept d’avis moyenne score (MOS). MOS est la mesure standard or pour évaluer la qualité audio. Il est représenté sous la forme d’une note de nombre entier de 0 à 5.

La base de toutes les mesures de qualité de voix est la façon dont une personne perçoit la qualité de voix. Car il est affecté par la perception humaine, il est fondamentalement subjectivement. Il existe plusieurs méthodologies de test subjectivement.
La plupart des mesures de qualité de voix sont basées sur une échelle d’évaluation (blocage) catégorisation absolue.

Dans un test subjectivement blocage, un nombre important de statistiques de personnes taux leur qualité de l’expérience sur une échelle de 1 (mauvais) à 5 (excellent). La moyenne des scores est la note MOS de qualité. La note MOS qualité qui en résulte dépend de la plage des expériences qui ont été exposés pour le groupe et le type de l’expérience d’évaluation.

Car il est difficile d’effectuer des tests subjectives de qualité de voix pour un système de communication live, équipes et Skype pour les entreprises génèrent valeurs MOS à l’aide des algorithmes pour prévoir objective les résultats d’un test subjectivement.

Le jeu disponible de MOS et mesures associé fournit une vue de la qualité de l’expérience remis aux utilisateurs.

En fournissant aux utilisateurs des périphériques certifiés pour les équipes et Skype pour les entreprises, vous réduisez la probabilité de rencontrer des expériences négatives en raison de l’appareil lui-même (qui est plus probable, par exemple, avec les microphones et les haut-parleurs intégrés). Pour plus d’informations, voir [téléphones et appareils pour Skype pour les entreprises](https://technet.microsoft.com/office/dn947482).

#### <a name="organizational-usage-of-capture-devices-microphones-by-volume"></a>Utilisation d’organisation de périphériques de capture (microphones) en volume

Ce rapport est utilisé pour évaluer l’utilisation d’un microphone en volume et la note MOS de qualité et peut être trouvé dans les modèles d’accompagnement sous Clients et périphériques *.*

> [!IMPORTANT]
> Rapports sur les périphériques vous obligent à exclure des données participants fédérées. Pour exclure les données participants fédérées, vous devez ajouter un filtre de requête pour **Second ID client** de votre organisation [d’ID de client](#tenant-id). 

> [!NOTE] 
> Veillez à régler le filtre mois année au mois actuel. Sélectionnez **Modifier**, puis ajuster les **Mois année** pour enregistrer le nouveau mois par défaut.<br><br> Vous pouvez remarquer lorsque ce rapport que vous voyez le même périphérique signalé plusieurs fois. Il s’agit en raison de la façon dont le périphérique est indiqué dans CQD. Différences dans le matériel et les paramètres régionaux du système d’exploitation signaler les données du périphérique différent.

![Capture d’écran de l’état des périphériques (Microphone) dans le tableau de bord qualité des appels.](media/quality-of-experience-review-guide-image29.png)

_La figure 29 - – rapport de périphérique (Microphone)_

##### <a name="remediation"></a>Mise à jour

La première tâche consiste à déterminer la cible MOS que vous souhaitez atteindre. MOS scores compris entre 1 et 5, 5 correspondant à la meilleure. Choisissez une cible raisonnable en fonction de votre environnement et les résultats de la requête. Dans l’exemple suivant, la cible est un score MOS de 3.6 ou supérieur pour tous les périphériques qui ont plus de 100 flux. Vous obtiendrez une qualité de votre périphérique cible lorsque :

-   Les résultats de requête périphérique renvoient MOS \> 3.6 pour NumStreams \> 100

En règle générale, vous devez remplacer les périphériques médiocres avec les périphériques certifiés. Certaines considérations lors de la consultation du rapport de périphérique sont les suivantes :

-   Sont des périphériques certifiés ou connus a été vérifié dans votre environnement ? Si un périphérique certifié ou bon est retourné dans la requête avec un score MOS inférieur à votre planification, il est peut-être inconnus facteurs supplémentaires (comme un réseau mauvaise ou pc puissance) qui contribue au score faible.
    Enquête supplémentaire seront requis.

-   Vous pouvez identifier les utilisateurs d’un appareil via [Analytique d’appel](#call-analytics-training). Vérifiez pour vous assurer qu’ils ont les derniers pilotes de périphériques et que leur appareil n’est pas connecté via un concentrateur USB.

-   Vérifie s’il existe une corrélation entre les périphériques défectueux et création d’un système particulier et le modèle. Dans ce cas, le périphérique peut être incompatibles ou besoin des mises à niveau du pilote.

La deuxième tâche consiste à déterminer l’utilisation de périphériques non certifiés. Nous recommandons d’utiliser un périphérique certifié au moins 80 % de tous les flux audio.
Cette opération s’effectue mieux en exportant le rapport de périphériques vers Excel manuellement le calcul de l’utilisation de périphériques certifiés ou approuvés. Les organisations conservent généralement une liste de tous les périphériques approuvées, filtrage et tri des données doivent être simples.

## <a name="appendix-a-lync-networking-guide"></a>Guide de mise en réseau annexe Lync A.

Pour plus d’informations sur les équipes et Skype pour des concepts de réseau d’entreprise et les raisons justifiant leur importance à la qualité, le [Guide de mise en réseau de Lync Server 2013](https://blogs.technet.microsoft.com/nexthop/2013/06/03/lync-server-2013-networking-guide-network-planning-monitoring-and-troubleshooting-with-microsoft-lync-server/) est toujours applicables.

## <a name="appendix-b-network-performance-requirements"></a>Exigences de performances annexe réseau B.

La qualité des médias en temps réel (audio, vidéo et partage d’application) sur IP est considérablement affectée par la qualité de la connectivité réseau de bout en bout. Des équipes ou des Skype pour la qualité des médias optimales, votre réseau doit respecter les mesures de performances réseau suivantes.

_Le tableau 11 - des exigences de performances réseau_

| Mesure                           | Client vers Microsoft Edge           | Périphérie client vers Microsoft Edge    |
|----------------------------------|------------------------------------|------------------------------------|
| Latence (unidirectionnelle)                | \<50 ms                            | \<30 ms                            |
| Latence (durée aller-retour ou temps d’aller-retour) | \<100 ms                           | \<60 ms                            |
| Perte de paquets en rafale                | \<10 % au cours de l’intervalle de 200-ms   | \<1 % au cours de l’intervalle de 200-ms    |
| Perte de paquets                      | \<1 % au cours de l’intervalle de 15-s    | \<0,1 % au cours de l’intervalle de 15-s  |
| Gigue arrivée entre des batteries de paquets      | \<30 ms pendant l’intervalle de 15-s | \<15 ms pendant l’intervalle de 15-s |
| Réorganisation des paquets                   | \<paquets d’ordre 0,05 %       | \<paquets d’ordre 0,01 %      |

Pour plus d’informations, consultez l’article suivant sur [média qualité et les performances réseau](https://aka.ms/performancerequirements) pour les équipes et Skype pour Business Online.

<a name="other-resources"></a>

## <a name="appendix-c-other-resources"></a>Annexe C. Autres ressources

### <a name="building-data-file"></a>Fichier de données de création

-   [Activation et à l’aide de CQD dans Skype pour Business Online](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-in-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)

<a name="CQD-training"></a>

### <a name="cqd-training"></a>Formation CQD

-   <https://aka.ms/sof-cqd>

-   Guide de [mise en route avec CQD](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Configuring%20Call%20Quality%20Dashboard%20to%20monitor%20your%20Skype%20for%20Business%20Online%20Environment) et atelier.

-   [CQD Dimensions et mesures guide en ligne](https://support.office.com/article/Dimensions-and-measures-available-in-Call-Quality-Dashboard-in-Skype-for-Business-Online-e97aeeee-9e43-416f-b433-9cdd63d8874b)

### <a name="call-analytics-training"></a>Appel de formation Analytique

-   [Présentation Analytique d’appel](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)

-   [Configurer l'analyse des appels Skype Entreprise](https://support.office.com/article/Set-up-Skype-for-Business-Call-Analytics-FBF7247A-84AE-46CC-9204-2C45B1C734CD)

-   [En quoi l'analyse des appels et le tableau de bord de qualité des appels sont-ils différents ?](https://support.office.com/article/What-s-the-difference-between-Call-Analytics-and-Call-Quality-Dashboard-4CD5FE35-8463-4996-A252-086CD3CA2D9A)

-   [Utiliser l'analyse des appels pour résoudre les problèmes liés à la qualité médiocre des appels Skype Entreprise](https://support.office.com/article/Use-Call-Analytics-to-troubleshoot-poor-Skype-for-Business-call-quality-66945036-ae87-4c08-a0bb-984e50d6b009)

### <a name="call-analytics-support"></a>Appelez le support technique Analytique

-   Communauté : [Skype pour le programme Aperçu](https://techcommunity.microsoft.com/t5/Skype-for-Business-Preview/bd-p/SkypeforBusinessPreviewProgram)

-   Pour obtenir une assistance, connectez-vous à notre portail de preview [www.skypepreview.com](http://www.skypepreview.com), sélectionnez **un problème de rapport**et utiliser l’option **Créer un nouveau bogue** pour signaler un problème. Veuillez noter que les techniciens du support technique sont disponibles pour prendre en charge du lundi au vendredi, de 6 heures à 9 h 00 EST. Demandes en dehors de ces heures triage seront le jour suivant.

### <a name="devices"></a>Périphériques

-   [Skype pour les Solutions métiers du catalogue de périphériques personnels & PC](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

### <a name="tenant-reporting"></a>Création de rapports de client

-   [Pack de contenu Office 365 d’Adoption](https://blogs.office.com/2017/05/22/announcing-the-public-preview-of-the-office-365-adoption-content-pack-in-powerbi/)

-   [Création de rapports Skype Entreprise Online](https://support.office.com/article/Skype-for-Business-Online-reporting-4935cddf-fafa-442d-91a3-246af01f8373)

-   [Microsoft Teams création de rapports](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/New-usage-reports-for-Microsoft-Teams/ba-p/132614)
