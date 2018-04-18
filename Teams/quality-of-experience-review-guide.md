---
title: Qualité de Guide de révision d’expérience des équipes de Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 04/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Guide pour l’analyse des performances multimédia en temps réel pour Microsoft Teams à l’aide du tableau de bord de qualité appeler (CQD).
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 42af71e9062b68da6e9d3bc77a6c067eee35ec92
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2018
---
# <a name="quality-of-experience-review-guide"></a>Qualité de Guide de révision d’expérience

Ce guide est la phase de lecteur de valeur pour Teams de Microsoft et Skype pour l’activité en ligne. Vous pouvez [télécharger une version de Word](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) de ce guide.

## <a name="introduction"></a>Introduction

Pour que le plus grand impact sur l’amélioration de l’expérience utilisateur, les organisations doivent mettre les domaines clés qui sont affichés dans la figure suivante.
Des zones supplémentaires incluent identifiant les tâches opérationnelles, la fixation d’objectifs pour les mesures de qualité, déterminer les mesures à utiliser pour évaluer le succès de l’organisation et restrictive des zones d’enquête en fonction des besoins.

![Domaines clés de la qualité de l’expérience utilisateur incluent l’audio, la fiabilité, enquêtes de l’utilisateur, les périphériques et les clients.](media/quality-of-experience-review-guide-image1.png)

_Figure 1 : clé opérationnelle vous trouverez tout au long de ce document_

En évaluant en permanence et en corriger les zones décrites dans ce document, vous pouvez réduire leur potentiel d’impact négatif sur la qualité de l’expérience de vos utilisateurs. La plupart des problèmes d’expérience utilisateur rencontré dans un déploiement peuvent être regroupées dans les catégories suivantes :

-   Configuration de pare-feu ou proxy incomplète

-   Une mauvaise couverture de Wi-Fi

-   Bande passante insuffisante

-   VPN

-   Versions client incompatibles ou obsolètes

-   Périphériques audio non optimisées ou intégrés

-   Sous-réseaux problématiques ou des périphériques réseau

Grâce à une planification et conception avant de déployer des équipes ou Skype pour professionnels en ligne, vous pouvez réduire le volume de travail qui est requis pour mettre à jour les expériences de haute qualité.

Ce guide se concentre sur l’utilisation en ligne du tableau de bord de qualité appeler (CQD) comme outil principal pour signaler et examinez chaque zone, avec un accent particulier sur audio afin d’optimiser l’adoption et à l’impact. Toute amélioration apportée au réseau afin d’améliorer l’expérience audio auront également directement des améliorations dans le partage de vidéo et de bureau.

Pour accélérer l’évaluation, les deux modèles CQD curated sont fournies : une pour la gestion de tous les réseaux et l’autre est filtré pour (internes) les réseaux gérés uniquement. Bien que les modèles de rapport de tous les réseaux sont configurés pour afficher des informations de réseau et de la construction, il peut toujours être utilisé pendant que vous travaillez à la collecte et de chargement des informations de construction. Téléchargement d’informations dans le CQD permet le service afin d’améliorer le rapport en ajoutant des informations de construction, de réseau et d’emplacement personnalisées lors de la différenciation interne de sous réseaux externes. Pour plus d’informations, consultez [mappage de construction](#building-mapping) plus loin dans ce document.

### <a name="what-is-the-cqd"></a>En quoi consiste le CQD ?

Vous utilisez le tableau de bord de qualité appeler (CQD) pour obtenir un aperçu de la qualité des appels effectués à l’aide des équipes et Skype pour les services. CQD est conçu pour aider les Skype pour les administrateurs d’entreprise et les équipes et les ingénieurs réseau optimisent le réseau. CQD examine agrègent les informations pour toute une organisation où les modèles globaux peuvent devenir apparents, autorisant le personnel à évaluer informé de la qualité des appels. CQD fournit des rapports de mesures d’appel qui vous donnent un aperçu de la qualité globale de l’appel, appel fiabilité et l’expérience de l’utilisateur.

> [!NOTE]
> CQD ne contient pas les informations d’identification personnelle (PII). Informations personnelles sont des informations qui peuvent être utilisées seul ou avec d’autres informations pour identifier, contacter ou localiser une seule personne, ou pour identifier un individu dans le contexte. 

### <a name="intended-audience"></a>Public visé

Ce document est destiné à être utilisé par les parties prenantes des partenaires et des clients avec les rôles de Collaboration/architecte en chef, Consultant, spécialiste de gestion/Adoption de modification, entraîner de Business Desk ou l’aide de la prise en charge, câble réseau, responsable du bureau et l’administration informatique.

Ce document est également destiné à être utilisé par les champion(s) de qualité désignés.
Pour plus d’informations, voir [le rôle de spécialiste de la qualité](https://docs.microsoft.com/MicrosoftTeams/4-envision-plan-my-service-management#the-quality-champion-role).

## <a name="prerequisites"></a>Conditions requises

Avant d’utiliser ce guide, assurez-vous que vous avez le bon locataire [rôles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) afin que vous puissiez accéder à CQD.

-   **Rôle d’administrateur Global de office 365 :** Accède à toutes les fonctionnalités d’administration de la suite Office 365 de services dans votre plan, y compris Skype pour les entreprises.

-   **Skype pour le rôle d’administrateur :** Configure les Skype pour entreprise de votre organisation et est en mesure d’afficher tous les [rapports d’activité](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) dans le centre d’administration Office 365. Ce rôle est nécessaire même si vous déployez uniquement les équipes.

Vous pouvez également assigner le rôle suivant à un compte d’utilisateur Office 365 pour permettre l’accès aux fonctions de génération d’états uniquement.

-   **Signale le lecteur :** Pouvez permet d’afficher tous les [rapports d’activité](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) dans le centre d’administration Office 365, tous les rapports à partir du [pack de contenu Office 365 Adoption](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)et les rapports CQD.

Comprendre les concepts clés de CQD aide à optimise l’impact que vous pouvez apporter pour améliorer l’expérience de vos utilisateurs, équipes ou Skype pour entreprise en ligne.
Vous trouverez des ressources supplémentaires dans l' [annexe](#other-resources).

## <a name="what-is-quality"></a>Quelle est la qualité ?

Lorsque vous abordez la qualité dans Skype pour les entreprises et les équipes, il est important de définir le terme pour parvenir à une compréhension commune. Qualité, telles que définies ici, est une combinaison de service métriques et l’expérience utilisateur.

![Métriques de service sont composent des versions appel faibles taux, la fiabilité, / périphériques de points de terminaison et le client. Expérience de l’utilisateur final est constitué de la perception de l’utilisateur de la qualité de service.](media/quality-of-experience-review-guide-image2.png)

_Figure 2 : quelle est la qualité ?_

### <a name="define-your-target-metrics"></a>Définir les mesures de la cible

Cette section décrit les métriques de service principaux que nous utilisons pour évaluer comment services expérience de santé. En évaluant en permanence et en efforts pour conserver ces mesures ci-dessous cible de la commande, vous allez à garantir la que qualité de l’appel de façon cohérente et fiable de rencontrer vos utilisateurs. Pour vous aider à démarrer, les objectifs suivants sont fournis.
Examinons brièvement la différence entre un réseau managée et non managées :

-   Un réseau *géré* pouvant être influencé et contrôlé par l’organisation.
    Cela inclut le réseau local interne, le réseau étendu à distance et VPN.

-   Un réseau *non géré* ne peut pas être influencé ou contrôlé par l’organisation. Un exemple d’un réseau non géré est un réseau d’hôtel ou un aéroport.

_Tableau 1 : mesures de base cible fonctionnement évaluation_

|               | Qualité pour les réseaux gérés | Fiabilité des réseaux gérés |                      |
|---------------|------------------------------|----------------------------------|----------------------|
| Nom de mesure   | Audio faible appeler % de rapport      | Appelez le programme d’installation % d’erreurs            | Appelez le dépôt % d’erreurs |
| Cible de l’échantillon | \<3 %                         | \<1 %                             | \<4 %                 |

Il est important de discuter et de définir des cibles de votre organisation pour répondre aux objectifs de votre entreprise. Dans l’idéal, vous devez identifier ces cibles avant le déploiement.

#### <a name="audio-pcr-"></a>% PCR audio 

Audio médiocre appeler Ratio (PCR) représente le pourcentage global de l’organisation des appels qui ont une mauvaise qualité du son. Cette mesure vise à mettre en surbrillance les zones où votre organisation permet de vous concentrer les efforts pour que de grand impact pour réduire cette valeur et l’amélioration de l’expérience utilisateur, c’est pourquoi les réseaux gérés sont le principal objectif lors de la recherche à la PCR. Les utilisateurs externes sont trop importantes, mais les enquêtes diffère sur une base d’utilisateur et d’organisation.
Envisagez de fournir des méthodes conseillées pour les utilisateurs externes et examiner des appels externes indépendamment de l’organisation globale.

#### <a name="call-setup-failures-"></a>Appelez le programme d’installation % d’erreurs 

Il s’agit d’une session de média n’a pas pu être établie. Compte tenu de la gravité de l’impact sur l’expérience utilisateur mesurée ici, l’objectif est de réduire cette valeur comme proche de zéro que possible. Une valeur élevée pour cette mesure est plus courante dans les déploiements de nouvelles règles de pare-feu incomplète à un déploiement évolué, mais il est toujours important de surveiller régulièrement. Comme votre rigueur opérationnelle arrivera à échéance, vous pouvez développer cette mesure pour inclure des charges de travail vidéo et partage de bureau.

#### <a name="call-drop-failures-"></a>Appelez le dépôt % d’erreurs 

Cela s’applique à une charge de travail audio où la session s’est arrêtée de façon inattendue. Comme votre rigueur opérationnelle arrivera à échéance, vous pouvez développer cette mesure pour inclure des charges de travail vidéo et partage de bureau.

### <a name="service-metrics"></a>Métriques de service

Cibles de métriques de service se composent des mesures spécifiques basées sur le client.

#### <a name="pcr"></a>PCR

Pour déterminer si un appel est classifié comme une mauvaise est en utilisant le rapport de mauvaise appel (PCR). PCR est composé des cinq mesures de réseau décrits dans le tableau suivant. Pour un appel à être classées comme médiocres, qu’une mesure doit dépasse le seuil défini. Pour plus d’informations sur le processus de classification des appels, consultez [ce billet de blog](https://blogs.technet.microsoft.com/jenstr/2013/09/20/what-is-the-basis-for-classifying-a-call-as-poor-in-lync-2013-qoe/).

_Tableau 2 : métriques de Service appel médiocre_

| Mesure                                           | Description                                                                                                                                                                                                                                                                                                                                                                  | Expérience utilisateur                                                                                                                                                          |
|--------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Variation de la \>30 ms                                   | Il s’agit de la variation moyenne de retard entre les paquets successifs. Skype pour les entreprises et les équipes peuvent s’adapter à certains niveaux de gigue grâce à la mise en mémoire tampon. Il est uniquement lorsque la variation dépasse la mise en mémoire tampon qu’un participant constate les effets d’une gigue.                                                                                                                         | Les paquets qui arrivent à des vitesses différentes provoquent la voix d’un haut-parleur à son robotique.                                                                                       |
| Taux de perte de paquets \>0,1 ou 10 %                    | Cela est souvent définie comme un pourcentage de paquets sont perdus. Perte de paquets affecte directement la qualité audio, de taille réduite et personne paquets perdus qui ont presque pas d’impact à des pertes de transmission en rafale DOS à DOS qu’audio cause à découper complètement.                                                                                                                               | Les paquets sont perdus et d’arriver pas à leur destination faire apparaître des intervalles dans les médias, qui en résulte dans les mots et les syllabes manquées et instable, vidéo et partage. |
| Temps d’aller-retour de \>500 ms                         | C’est le temps que nécessaire pour obtenir un paquet IP du point A au point B et au point A. Ce délai de propagation réseau est lié à la distance physique entre les deux points et de la vitesse de la lumière et inclut des frais supplémentaires prises par les divers périphériques dans le chemin d’accès réseau.                                                                                  | Les paquets prend trop de temps à l’arrivée à destination de provoquer un effet de talkie-walkie.                                                                                 |
| Moyenne de dégradation NMOS \> 1.0                  | Un ou plusieurs de ces mesures réseau individuellement n’ont pas été médiocre, ensemble dû le réseau [Note d’Opinion moyenne](https://technet.microsoft.com/library/bb894481(v=office.12).aspx) (NMOS) pour déplacer plusieurs points. Cela ne signifie pas nécessairement la connexion réseau est mauvaise, mais suffisamment problèmes s’est produite lors de l’appel que la qualité a été réduite. | Il s’agit d’une combinaison de gigue, perte de paquets, et, à un degré moindre, augmente le temps d’aller-retour. L’utilisateur peut être confronté à une combinaison de ces symptômes.          |
| Taux moyen d’échantillons masqués \> 7 % ou 0,07 | Un ou plusieurs de ces mesures réseau individuellement n’ont pas été médiocre, dû au client d’autoréparation du support. Un échantillon audio masqué est une technique utilisée pour lisser la transition brutale devrait généralement être provoqué par paquets perdus.                                                                                                                | Des valeurs élevées indiquent que des niveaux significatifs de masquage de perte ont été appliquées et entraîné audio déformée ou perdue.                                                  |

#### <a name="client-and-device-readiness"></a>Préparation du client et du périphérique

Vous avez besoin d’une stratégie solide de client et du périphérique pour vous assurer que les utilisateurs disposent d’une expérience utilisateur positive et cohérente. Chaque stratégie de préparation de lecteur quelques principes clés.

##### <a name="client-readiness"></a>Préparation du client

Une stratégie de disponibilité du client fort garantit que les utilisateurs exécutent la version la plus récente du client tout en profitant du meilleur parti.
Microsoft correctifs régulièrement le Skype pour client d’entreprise ; veiller à ce que vous maintenir à jour dans votre environnement est essentiel pour votre réussite globale.

Nous vous recommandons de pas laisser vos versions client prendre du retard de plus de six mois. Si vous utilisez Office-Démarrer en un clic, vous êtes déjà en cours mis à jour par le service. Utilisez inclus [Rapport Client](#determine-client-versions), comme décrit plus loin dans ce guide, pour vous aider dans ce processus. Vous pouvez également exploiter les exemples de rapports taux mes appels pour renforcer votre stratégie de disponibilité du client.

> [!IMPORTANT]
> Actuellement, les clients d’équipes sont distribués et mis à jour automatiquement via le réseau de livraison de contenu Azure et est maintenu à jour par le service. Préparation du client et des activités d’enquêtes ne sont pas applicables aux équipes.


##### <a name="device-readiness"></a>Préparation du périphérique

Sans une stratégie unique peut affecter l’expérience utilisateur plus de votre stratégie de disponibilité du périphérique. La plupart des entreprises sont heureux de supprimer les périphériques inutiles des utilisateurs (par exemple, les téléphones de bureau ou les autres périphériques audio dédiées), et c’est souvent une justification core pour basculer vers les équipes ou Skype pour les entreprises. Toutefois, ces mêmes entreprises parfois hésitent à fournir des périphériques de remplacement, même si ces périphériques sont moins coûteux. Moderne portables et PC, bien équipés de microphone et haut-parleur, intégrés ne sont pas optimisé pour la voix de l’échelle de l’entreprise sur IP (VoIP). Cela crée souvent une mauvaise expérience pour tous les participants, en particulier si le haut-parleur est dans un environnement bruyant. Programme de certification de périphériques de Microsoft garantit que, lorsqu’un utilisateur participe à un appel téléphonique à l’aide de n’importe quel périphérique certifié pour les équipes ou Skype pour les entreprises, il produit une expérience qui est supérieure à un périphérique non certifié.

Nous vous recommandons toujours que Skype pour les utilisateurs professionnels et les équipes utilisent un casque certifié ou l’intervenant lorsque le participant à un appel vocal à l’aide d’un client de bureau.
Pour plus d’informations sur les périphériques certifiés de Microsoft, consultez cet [article sur les téléphones et périphériques qualifiés](https://technet.microsoft.com/office/dn788944.aspx). Utilisez le [Rapport de périphérique](#devices-investigations), plus loin dans ce guide, pour obtenir de l’aide à la gestion de vos périphériques. Vous pouvez également utiliser les exemples de rapports taux mes appels pour renforcer votre stratégie de disponibilité du périphérique.

### <a name="user-experience"></a>Expérience utilisateur

Analyse de l’expérience utilisateur est plus un art qu’une science, car les métriques rassemblées ici ne signifie toujours qu’il existe un problème avec le réseau ou d’un service, mais au lieu de cela, ils indiquent que l’utilisateur perçoit un problème. Microsoft propose un mécanisme d’enquête intégrée, connu en tant que taux de mon appel (RMC) : pour évaluer l’expérience utilisateur globale. RMC va vous aider à répondre aux questions suivantes à partir du point de vue des utilisateurs :

-   Savoir comment utiliser la solution ?

-   Est une solution conviviale et intuitive, et il prend en charge mes besoins de communication quotidienne ?

-   La solution aide-t-il me faire mon travail ?

-   Quel est mon perception globale de la solution ?

-   Puis-je utiliser la solution à n’importe quel point dans le temps, que je suis ?

-   Puis-je configurer et maintenir un appel ?

#### <a name="rmc"></a>RMC.

RMC est intégrée à des équipes et Skype pour les entreprises et est automatiquement configuré pour être affichée après une dans tous les appels de 10 ou 10 pour cent de tous les appels. Cette brève enquête demande à l’utilisateur d’évaluer l’appel et de fournir un contexte peu pour pourquoi la qualité des appels ont pu être médiocre. Une évaluation d’une ou deux est jugée insuffisante, trois à quatre est bonne et cinq est excellente. Bien qu’il soit quelque peu d’un indicateur en retard, il s’agit d’une mesure utile pour les problèmes découvrant les métriques de service peuvent être manquantes.

> [!NOTE]
> Jusqu'à ce que les utilisateurs sont invités à répondre à des enquêtes RMC en donnant une bonne rétroaction, en plus des réponses incorrectes, généralement revenir très lourdement négatif. La plupart des utilisateurs ne répondre que lors de l’appel de qualité est mauvaise. De ce fait, vos rapports RMC peuvent inclinés vers le mauvais côté, même si les métriques de service sont bonnes. 


Vous pouvez utiliser CQD pour générer des rapports sur les réponses de l’utilisateur RMC et des exemples de rapports sont inclus dans le modèle CQD. Toutefois, ils ne sont pas décrites en détail dans ce guide. Pour plus d’informations sur le centre RMC à Skype pour entreprise en ligne et le Guide de sensibilisation des utilisateurs à donner les réponses RMC utiles, consultez ce [blog valider](https://blogs.technet.microsoft.com/jenstr/2015/05/05/rate-my-call-in-skype-for-business-2015/).

### <a name="categories-of-quality"></a>Catégories de qualité

La réussite d’un déploiement fiable et de qualité à mettre en application dépend de votre rigueur opérationnelle du bâtiment. En particulier, une attention particulière aux trois catégories illustrées dans la figure suivante ; Il s’agit de l’objectif de ce guide :

-   **Réseau :** Qualité audio consacré à la métrique PCR, de l’utilisation TCP, de sous-réseaux filaires et sans fil et l’identification de l’utilisation de serveurs proxy HTTP et VPN.

-   **Points de terminaison :** Périphériques audio et la version du client (Skype pour entreprise uniquement).

-   **Gestion des services :** Cette catégorie comprend deux sections :

    -   Tout d’abord incombe de Microsoft pour gérer et maintenir les Skype et les équipes des services professionnels en ligne.

    -   Deuxième sont les tâches que votre organisation doit gérer pour garantir un accès fiable au service, telles que la mise à jour des informations de génération et de la maintenance des pare-feux de nouvelles adresses Office 365 IP comme l’infrastructure est ajouté au service.

![Les catégories de qualité dans une organisation : service de gestion des points de terminaison et le réseau.](media/quality-of-experience-review-guide-image3.png)

_Figure 3 : les catégories critiques pour les équipes et Skype pour le déploiement d’entreprise en ligne_

Le graphique ci-dessous présente les tâches que vous devez exécuter pour chaque catégorie. Nous vous conseillons d’exécuter ces tâches une fois par semaine, au minimum.

La première fois que vous effectuez ces tâches prendra plus d’efforts que les itérations suivantes, car la plupart de ces catégories nécessitent que vous validiez vos configurations de déploiement. Une fois que vous avez atteint l’état souhaité par les objectifs que vous avez définies, exécution de ces tâches vous aide à maintenir cet état.

#### <a name="service-management-tasks"></a>Tâches de gestion de service

Dans un monde du nuage d’abord, vous devez effectuer certaines tâches de gestion de service pour mettre à jour les expériences utilisateur de qualité. Ces tâches comprise, garantissant une bande passante suffisante pour atteindre le service sans saturer les liens internet, validation de qualité de service (QoS) est en place dans tous les domaines du réseau géré, et, enfin, d’excellentes [Office 365 IP plages sur pare-feu](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).

#### <a name="network-tasks"></a>Gestion du réseau

Il existe deux catégories de tâches réseau : fiabilité et qualité. La fiabilité se concentre sur la mesure de la capacité de l’utilisateur pour effectuer des appels avec succès et rester connecté. Qualité se concentre sur la télémétrie agrégée envoyé aux équipes et Skype pour entreprise en ligne par le client de l’utilisateur pendant et après la fin de l’appel.

Étant donné l’impact critique de fiabilité sur l’expérience de l’utilisateur, commencer à évaluer et étudier ces mesures avant de plonger dans la qualité.

#### <a name="endpoints-tasks"></a>Tâches de points de terminaison

La tâche principale de cette catégorie valide les versions client exécutent Skype pour les entreprises sur les builds de bureau à partir des six derniers mois afin de garantir des utilisateurs obtiennent l’avantage des optimisations apportées à la Skype pour client ordinateur de bureau d’entreprise en continu. En outre, cela simplifie les tâches de gestion client globale et offre une expérience utilisateur cohérente.

L’autre zone important est contrôle les périphériques qui sont les plus fréquentes dans votre déploiement et mise en œuvre des périphériques certifiés de fournir la meilleure expérience utilisateur.

> [!IMPORTANT]
> Actuellement, les clients d’équipes sont distribués et mis à jour automatiquement via le réseau de livraison de contenu Azure et est maintenu à jour par le service. Préparation du client et des activités d’enquêtes ne sont pas applicables aux équipes.


## <a name="using-the-reports"></a>Utilisation des rapports

Cette section décrit les notions de base de l’utilisation de CQD. Est fournie pour les rubriques suivantes :

-   Recherche de votre ID client

-   Création de rapports sur les équipes et Skype pour entreprise

-   Première et deuxième catégories

-   Dimensions, les mesures et les filtres

-   Flux de données par rapport à des appels

-   Appelle une bonne et une mauvaise non classifié

-   Mise en route CQD

-   Modification de rapports de CQD

-   Filtrage des rapports de CQD

Pour les ressources et formations plus approfondies, reportez-vous à l' [annexe](#other-resources).

### <a name="tenant-id"></a>ID de clients

Certains rapports CQD nécessitent que vous incluez un filtre pour votre code de client. En raison de la façon dont CQD regroupe des données, fédéré télémétrie participant est inclus.
Bien que ceci peut s’avérer utile lors de l’analyse des métriques d’appel médiocre, client et dispositif de rapports nécessitent le filtrage de données à un client spécifique à exclure fédéré de télémétrie participant. Si vous ne connaissez pas votre ID client, vous pouvez utiliser une des méthodes suivantes pour le trouver.

Autorisations requises

-   Rôle Administrateur général

-   Skype pour le rôle d’administrateur

#### <a name="azure-ad-portal"></a>Azure Portal de publicité

1.  Connectez-vous au portail Microsoft Azure :<https://portal.azure.com>

2.  Sélectionnez **Azure Active Directory**.

3.  **Gérer**, cliquez sur **Propriétés**. L’ID de client est affiché dans la zone **ID de répertoire** .

#### <a name="azure-powershell"></a>PowerShell Azure

1.  [Installez le module de gestion des services Microsoft Azure PowerShell](https://docs.microsoft.com/powershell/azure/servicemanagement/install-azure-ps?view=azuresmps-4.0.0).

2.  Ouvrez une fenêtre de commande PowerShell d’Azure et exécutez le script suivant, entrez vos informations d’identification de Office 365 lorsque vous y êtes invité :  
    **Connexion-AzureRmAccount**

3.  L’ID de client est répertorié dans la sortie.

#### <a name="skype-for-business-online-admin-center"></a>Skype pour le centre d’administration en ligne de Business

1.  Atteindre<https://portal.office.com>

2.  Connectez-vous avec un compte d’administrateur d’organisation cliente.

3.  Sélectionnez **Skype pour entreprise** dans le **Centre d’administration**.

4.  L’ID de client est répertorié en tant **qu’ID de l’organisation** sur la page d’accueil.

#### <a name="skype-for-business-online-using-powershell"></a>Skype pour Business Online à l’aide de PowerShell

1.  [Se connecter sur Skype pour les entreprises en ligne via PowerShell](https://technet.microsoft.com/library/dn362839(v=ocs.15).aspx).

2.  Exécutez la commande suivante :  
    **(Get-cstenant) .tenantid**

3.  L’ID de client est affiché en tant que GUID.

### <a name="teams-vs-skype-for-business"></a>Équipes et Skype pour entreprise

CQD pouvez signaler sur les équipes et Skype pour télémétrie d’entreprise. Toutefois, il peut être amené à développer un rapport à examiner la télémétrie d’équipes distinct de Skype pour les entreprises.

#### <a name="summary-reports"></a>Rapports de synthèse

Pour modifier la page de rapports de synthèse pour consulter uniquement les équipes ou Skype pour entreprise, sélectionnez le menu déroulant de **Filtre de produit** à partir du haut de l’écran, puis sélectionnez le produit que vous souhaitez.

![Capture d’écran de l’appeler tableau de bord qualité reflétant une liste déroulante affichant l’option Filtrer par charge de travail.](media/quality-of-experience-review-guide-image4.png)

_Figure 4 : sélectionnez un filtre de produit_

#### <a name="detailed-reports"></a>Rapports détaillés.

Pour filtrer un rapport détaillé, ajouter le filtre **Les équipes est** à l’état et affectez-lui la valeur True ou False. Pour plus d’informations, consultez [modification des rapports](#editing-reports) plus loin dans cette section.

![Capture d’écran de l’appeler tableau de bord qualité représentant le serveur de fichiers qui peut être ajouté à un rapport détaillé.](media/quality-of-experience-review-guide-image5.png)

_Figure 5 : ajout d’un filtre de le Teams de Microsoft dans un rapport_

### <a name="dimensions-measures-and-filters"></a>Dimensions, les mesures et les filtres

Une requête CQD bien formée contienne les trois paramètres suivants :

-   **Dimension :** Comment faire sur les données de tableau croisé dynamique.

-   **Mesure :** Ce que je veux créer un rapport.

-   **Filtre :** Comment souhaitez réduire la requête renvoie le jeu de données.

Une autre façon de considérer ceci est une dimension est la fonction de regroupement et une mesure est dans les données que je suis intéressé par un filtre, c’est comment limiter les résultats à ceux qui sont pertinentes à ma requête.

Est un exemple d’une requête bien formé « afficher les flux faibles [unité] par sous-réseau [Dimension] pour la génération 6 [filtre]. »

Pour plus d’informations, voir [Dimensions et les mesures disponibles dans CQD](https://aka.ms/cqd-dm).

Pour les dimensions, mesures et des filtres pour les rapports utilisés dans les modèles CQD, reportez-vous à l' [annexe](#CQD-training).

### <a name="first-vs-second"></a>Première et deuxième 

La plupart des dimensions et mesures dans CQD sont classées comme première ou deuxième.
CQD n’utilise pas les champs appelant/appelé, celles-ci ont été renommés _premier_ et _deuxième_ car il existe des étapes intermédiaires entre l’appelant et l’appelé. La logique suivante détermine quel point de terminaison du flux ou de l'appel est étiqueté comme premier :

-   Tout d’abord sera toujours un point de terminaison de serveur (serveur de conférence, serveur de médiation, etc.) si un serveur est impliqué dans le flux de données ou l’appel.

-   Deuxième sera toujours un point de terminaison client sauf si le flux est entre deux points de terminaison de serveur.

-   Si les deux extrémités sont du même type, le choix d’est la première est basée sur le classement interne de la catégorie de l’agent utilisateur. Cela garantit la cohérence de l'organisation.

Pour plus d’informations sur la détermination de la première ou la deuxième point de terminaison lorsqu’ils sont identiques, voir [Dimensions et les mesures disponibles dans CQD](https://aka.ms/cqd-dm).

### <a name="stream-vs-call"></a>Flux de données et l’appel

Vous devez comprendre la différence entre un appel et un flux de données correctement choisir les dimensions ou les mesures que vous consulterez dans CQD.

**Flux :** Il existe un flux de données entre deux points de terminaison. Un seul flux de données pour chaque direction, et deux flux sont requis pour la communication. Les flux sont utiles pour analyser les bâtiments ou les réseaux. Dans certains cas, les appels et les flux sont utilisés dans le nom (par exemple, le flux de configuration d’appel ou le flux d’ignorés appel).
Ils sont toujours classés comme des flux de données unique.

**Appeler :** Un appel est un regroupement de tous les flux de tous les participants. Un appel se compose de : au minimum, deux flux. Un seul appel aura deux participants avec un minimum d’un flux de données. Les appels sont utiles pour analyser les tendances dans le temps.

Pour obtenir des conseils supplémentaires sur si la dimension ou la mesure se rapporte à un appel ou un flux de données, voir les [Dimensions et les mesures disponibles dans CQD](https://aka.ms/cqd-dm)

### <a name="good-poor-and-unclassified-calls"></a>Appelle une bonne et une mauvaise non classifié

Un appel est classé soit bonne, mauvaise ou non classés. Prenons un instant pour parler de chacun d’eux de façon plus détaillée.

**Bonne ou mauvaise :** Un appel de bonne ou de mauvaise se compose d’un appel qui contient un jeu complet de métriques de service, pour lequel un rapport QoE complet a été généré.
Pour déterminer si un appel est bonne ou mauvaise est décrite [plus haut dans ce guide](#pcr).

**Non classés :** Un appel non classé ne contient pas un jeu complet de métriques de service. Il s’agit souvent des appels courts, généralement moins de 60 secondes, où moyennes n’a pas pu être calculées, et un rapport QoE n’a pas été généré.

### <a name="access-cqd-online"></a>Accès CQD

Vous pouvez accéder à CQD de deux manières.

-   Accédez à <https://cqd.lync.com>.

-   Accédez à **Skype pour le centre d’administration Business** \> **Outils**, puis sélectionnez le lien vers CQD, comme illustré ci-dessous.

![Capture d’écran affichant « outils » est sélectionnés dans le volet de navigation de gauche et le lien vers les « Skype pour entreprise en ligne appeler tableau de bord qualité » sélectionnée.](media/quality-of-experience-review-guide-image6.png)

_La figure 6 – accès CQD via le Skype pour Business admin center_

### <a name="getting-started"></a>Prise en main

Lorsque vous accédez d’abord à CQD, vous verrez la page de rapports de synthèse. La plupart des rapports décrits dans ce guide est des rapports personnalisés détaillés. Pour commencer à utiliser les rapports détaillés, sélectionnez **Les rapports de synthèse** en haut de la page, puis sélectionnez **Rapports détaillés**.

![Capture d’écran de l’appel du tableau de bord qualité depcting les différents types de rapports disponibles.](media/quality-of-experience-review-guide-image7.png)

_Figure 7 : accéder à des rapports détaillés._

La page Rapports détaillés dans CQD ressemble à la figure ci-dessous.

![Capture d’écran de la page de rapport détaillé dans CQD et les différents éléments qui composent un rapport.](media/quality-of-experience-review-guide-image8.png)

_Figure 8 : page de rapports détaillés._

1.  Le volet Résumé affiche le contexte pour l’ensemble du rapport qui s’affiche à droite.

2.  Vous pouvez sélectionner **Modifier** dans le volet de résumé pour définir les propriétés au niveau du rapport (y compris la hauteur de l’axe des y).

3.  Le plan du site permet aux utilisateurs d’identifier leur emplacement actuel dans la hiérarchie de l’ensemble du rapport.

4.  Les rapports ayant des rapports de l’enfant sont affichées avec un lien bleu. En cliquant sur le lien, vous pouvez accéder le rapports enfant.

Pointez sur les graphiques à barres et des courbes de tendance pour afficher les valeurs détaillées. L’état qui a le focus affiche le menu action : **Modifier**, **Clone**, **Supprimer**, **Télécharger**et **Arborescence d’exporter un rapport**.

### <a name="editing-reports"></a>Modification de rapports

Lorsque vous sélectionnez l’option **Modifier** dans le menu action d’un rapport, vous allez ouvrir l’éditeur de requête. Chaque rapport est sauvegardée par une requête. Il s’agit de la visualisation des données renvoyées par la requête. L’éditeur de requête est une interface utilisateur pour la modification de ces requêtes en plus les options d’affichage de l’état, comme illustré dans la figure suivante.

![Capture d’écran de la page de rapport détaillé dans CQD et les différents éléments qui composent un rapport lorsque le rapport est en cours de modification.](media/quality-of-experience-review-guide-image9.png)

_Figure 9 : éditeur de rapport_

1.  Vous choisissez des filtres, des mesures et des dimensions dans le volet de gauche. Pointe vers une valeur existante affiche un bouton Fermer (**X**), que vous pouvez choisir de supprimer la valeur.

    1.  En sélectionnant la dimension ou la mesure, vous pouvez modifier le titre en modifiant le champ **titre** . Vous pouvez également modifier l’ordre en sélectionnant le bleu vers le haut ou vers le bas des flèches dans le volet supérieur.

    2.  Sélection (**+**) en regard d’un titre de la boîte de dialogue pour ajouter une nouvelle dimension, une mesure ou un filtre.

    3.  Entrez les premières lettres de la dimension, une mesure ou un filtre dans le **de trouver un** champ pour filtrer la liste de recherche plus facile.

2.  Le volet supérieur affiche les options de personnalisation de graphique.

3.  L’éditeur de requête affiche un aperçu du rapport.

4.  Utilisez la zone **Modifier** en bas de l’écran pour créer ou modifier une description détaillée du rapport.

### <a name="filtering-reports"></a>Filtrage de rapports

Les modèles fournis inclut plusieurs requêtes prédéfinies et les filtres de rapport. Les sections suivantes décrivent les filtres courants utilisés dans les modèles.

#### <a name="cqd-filter"></a>Filtre de le CQD

Vous pouvez utiliser le filtre de le CQD, ou le filtrage d’URL, filtrer temporairement de chaque requête de rapport. Le filtre CQD plus courantes que vous allez utiliser est pour filtrer les rapports pour exclure fédéré de télémétrie participant. Il est recommandé que vous associez un signet à ce filtre afin qu’il devienne l’affichage par défaut. Exclusion de données fédérées dans des rapports de la CQD est utile lorsque vous êtes couronnée de bâtiments gérés ou des réseaux où des données fédérées susceptibles d’influencer votre rapport.

Pour implémenter un filtre de le CQD, dans la barre d’adresse du navigateur, ajoutez le code suivant à la fin de l’URL :

/Filter/ [AllStreams]. [Id de clients deuxième] \|[Votre client ID ici]

**Exemple :**  
https://cqd.lync.com/cqd/\#/ 02-1234567/2018/filtre / [AllStreams]. [Id de clients deuxième] \|[TENANTID] & clients = TENANTID

> [!NOTE]
> L’exemple d’URL ci-dessus est pour une représentation visuelle uniquement. Veuillez utiliser le lien CQD par défaut de <https://cqd.lync.com>.

#### <a name="query-filters"></a>Filtres de requête

Les filtres de requête sont implémentées à l’aide de l’éditeur de rapport. Ces filtres permettent de réduire le nombre d’enregistrements retourné par CQD, ce qui réduit la taille globale de l’état. Ceci est particulièrement utile pour le filtrage des réseaux non managés.
Les filtres ci-dessous utilisent les expressions régulières (RegEx).

_Tableau 3 : les filtres de requête_

| Filtre               | Description          | Exemple de filtre de requête CQD                                  |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|
| Valeurs non renseignées         | Certains filtres n’ont pas la possibilité de filtrer les valeurs vides. Pour filtrer des valeurs vides manuellement, utilisez l’expression vide et la valeur du filtre est égal à ou différent de, selon vos besoins.                                                                                                                             | Nom de la deuxième génération \< \> \^ \\s\*\$                       |
| Sous-réseaux domestiques les plus courants | Sans fichier de construction valide pour séparer géré à partir de réseaux non managés, réseaux domestiques seront incluses dans les rapports. Ces sous-réseaux domestique est en dehors de la portée de son contrôle et peut être exclus rapidement un rapport. Les sous-réseaux domestiques les plus courants, tels que définis dans ce guide, sont 10.0.0.0, 192.168.1.0 et 192.168.0.0. | Deuxième sous-réseau \< \> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Intérieur et l’extérieur   | Utilisé pour filtrer un rapport (à l’intérieur) managé ou non managé (en dehors). Le modèle CQD managé est déjà préconfiguré avec ces filtres.                                                                                                                                                                                | Ensuite, à l’intérieur de Corp = à l’intérieur                               |

#### <a name="report-filters"></a>Filtres de rapport

Les filtres de rapport sont implémentées par l’ajout d’un filtre dans le rapport rendu soit dans l’éditeur de rapport ou directement dans le rapport. Les filtres de rapports suivants sont utilisés dans le modèle.

_Tableau 4 : filtre du rapport_

| Filtre     | Description                            | Exemple de filtre de rapport CQD         |
|------------|----------------------------------------|-----------------------------------|
| Month      | Démarrer avec l’année en premier, puis les mois. | 2017-10                           |
| Alphabétique | Filtres pour les caractères alphabétiques. | [a-z]                             |
| Numérique    | Filtres pour n’importe quel caractère numérique.    | [0-9]                             |
| Pourcentage | Filtres pour un pourcentage.              | ([3-9]\\.) \|([3-9])\|([1-9][0-9]) |

## <a name="import-the-cqd-templates"></a>Importer les modèles CQD

Ce guide inclut [deux modèles CQD curated](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-lite-templates-v-1-2.zip?raw=true). Ces modèles d’accélèrent l’utilisation de CQD et vous permettent de valoriser rapidement les capacités de CQD pour un impact sur vos utilisateurs équipes ou Skype pour une expérience. Le modèle de tous les réseaux, mais optimisé pour fonctionner avec un bâtiment fichier de données peut être utilisé pendant que vous travaillez à la collecte et de chargement des informations de construction dans CQD, comme décrit dans la section suivante.

**Pour importer les modèles (. CQDX) en CQD en ligne**

1.  Accédez à <https://cqd.lync.com>.

2.  S’authentifier à l’aide de vos informations d’identification d’administration de Office 365.

> [!NOTE]
> Vous devez avoir Office 365 administrateur Global, Skype pour administrateur de l’entreprise ou rôle de lecteur du rapport pour accéder à CQD. 


3.  Sélectionnez le menu **Rapports Résumé** en haut de la page et choisissez **Des rapports détaillés**.

4.  Dans le volet Sommaire, sélectionnez **Importer**. Aller à la CQDX enregistrée d’emplacement, sélectionnez le modèle CQDX et puis sélectionnez **Ouvrir**.

5.  Une fois que le modèle est téléchargé, une fenêtre contextuelle affiche le message « Importation du rapport a réussi ». Sélectionnez **OK.**

![Capture d’écran d’une fenêtre contextuelle qui informe l’utilisateur que le modèle a été importé avec succès.](media/quality-of-experience-review-guide-imagestep5.png)

6.  Répétez les étapes 4 et 5 pour le deuxième modèle CQD.

> [!NOTE]
> Importer les modèles CQD par l’utilisateur. Si d’autres utilisateurs doivent utiliser le rapport, ils doivent se connecter et importez-les dans leur instance CQD. 


## <a name="building-mapping"></a>Mappage de construction

En une équipe ou Skype pour le déploiement d’entreprise en ligne, tous les clients externes.
Qui a les conséquences que par défaut, tous les clients sont signalés comme à l’extérieur dans CQD en ligne, indépendamment de si le client a été connecté sur un réseau d’entreprise interne.

Lorsque vous travaillez avec la qualité des appels, vous devez connaître l’emplacement d’un client, et si elle a été connecté à un réseau, vous pouvez gérer ou un réseau ne sont pas disponibles, l’hypothèse étant que vous pouvez améliorer les réseaux seulement vous pouvez gérer.
En téléchargeant le réseau et les informations de construction pour CQD en ligne, vous permettez de CQD déterminer si un client a été connecté à un réseau interne d’entreprise/géré ou à un réseau externe/managé.

### <a name="building-data-file-structure"></a>Structure de fichier de données de construction

Le format du fichier de données que vous chargez doit répondre aux exigences suivantes pour transmettre le contrôle de validation avant de le télécharger.

-   Le fichier doit être un fichier TSV, ce qui signifie que pour chaque ligne, chaque colonne est séparée par une tabulation, ou un fichier CSV dans lequel chaque colonne est séparée par une virgule.

-   Le fichier ne peut pas être supérieur à 50 Mo.

-   Le contenu des données du fichier *ne doit pas inclure les en-têtes de tableau*. En d’autres termes, la première ligne du fichier de données doit être des données réelles, pas les en-têtes de colonne comme « Réseau ».

-   Pour chaque colonne, le type de données ne peut y Bool, nombre ou chaîne. Si le type de données est un nombre, la valeur doit être une valeur numérique ; s’il s’agit de Bool, la valeur doit être 0 ou 1.

-   Pour chaque colonne, si le type de données est la chaîne, les données ne peuvent être vides (mais toujours, doivent être séparées par un délimiteur approprié, qui est un caractère de tabulation ou une virgule). Cela affecte uniquement ce champ une valeur de chaîne vide.

-   Il doit y avoir 14 colonnes de chaque ligne. Chaque colonne doit avoir le type de données décrit dans le tableau suivant, et que les colonnes doivent être dans l’ordre indiqué dans le tableau.

_Tableau 5 : création de la structure de fichier_

| Nom de la colonne        | Type de données | Exemple                   | Conseils    |
|--------------------|-----------|---------------------------|-------------|
| Réseau            | Chaîne    | 192.168.1.0               | Obligatoire    |
| Nom_réseau        | Chaîne    | États-Unis/Seattle/SEATTLE-SEA-1 | Obligatoire\*  |
| NetworkRange       | Numéro    | 26                        | Obligatoire    |
| BuildingName       | Chaîne    | SEATTLE-SEA-1             | Obligatoire\*  |
| OwnershipType      | Chaîne    | Contoso                   | Facultatif    |
| BuildingType       | Chaîne    | Arrêt de l’informatique            | Facultatif    |
| BuildingOfficeType | Chaîne    | Ingénierie               | Facultatif    |
| Ville               | Chaîne    | Seattle                   | Recommandation |
| Code postal            | Chaîne    | 98001                     | Recommandation |
| Pays            | Chaîne    | NOUS                        | Recommandation |
| État              | Chaîne    | WA                        | Recommandation |
| Région             | Chaîne    | MSU                      | Recommandation |
| InsideCorp         | Bool      | 1                         | Obligatoire    |
| ExpressRoute       | Bool      | 0                         | Obligatoire    |

\*Bien que non obligatoire par CQD, les modèles sont configurés pour afficher le bâtiment et le réseau nom.

#### <a name="supernetting"></a>Création de super-réseaux

Vous pouvez utiliser la gestion de super-réseaux, couramment appelée inter-Domain Routing (CIDR), à la place de la définition de chaque sous-réseau. Un *supernet* est une combinaison de plusieurs sous-réseaux qui partagent un préfixe de routage unique. Au lieu d’ajouter une entrée pour chaque sous-réseau, vous pouvez utiliser l’adresse de super-réseaux/CIDR. Création de super-réseaux est pris en charge, mais nous ne vous recommandons d’utiliser.

Par exemple, construction de marketing de Contoso est constituée par les sous-réseaux ci-dessous :

-   10.1.0.0/24 – premier étage

-   10.1.1.0/24 – deuxième étage

-   10.1.2.0/24 – troisième étage

-   10.1.3.0/24 – quatrième de sol

Au lieu d’ajouter une entrée pour chaque sous-réseau, vous pouvez utiliser l’adresse de super-réseaux/CIDR, dans cet exemple, 10.1.0.0/22.

-   Réseau = 10.1.0.0

-   Plage réseau = 22

Voici quelques éléments à prendre en compte avant d’implémenter des super-réseaux :

-   Création de super-réseaux prend moins de temps en amont, mais cela compromet la réduction de la richesse de vos données. Supposons qu’il existe un problème de qualité impliquant sous-réseau 200.1.2.0. Si vous implémenté super-réseaux, vous ne saurez où se trouve le sous-réseau dans le bâtiment ou quel type de réseau est (par exemple, il s’agit d’un laboratoire). Si vous avez défini tous les sous-réseaux pour un bâtiment et télécharger des informations d’emplacement de plancher, vous ne pourrez pas voir cette distinction.

-   Il est important de s’assurer que l’adresse de super-réseaux/CIDR est correct et qu’il n’est pas l’interception de sous-réseaux indésirables.

-   Création de super-réseaux peut être utilisée dans un mappage de construction avec un masque de bits 8 à 28 bits.

-   Il est fréquent de trouver 192.168.0.0 dans les données. Pour de nombreuses organisations, cela indique que l’utilisateur est à la maison. Pour d’autres, c’est le schéma d’adresse IP pour une succursale. Si votre organisation possède des bureaux qui utilisent cette configuration, ne l’inclure dans votre fichier de génération comme il est difficile de faire la distinction entre des réseaux domestiques et internes à l’aide de sous-réseaux communs.

> [!IMPORTANT]
> La plage réseau peut être utilisée pour représenter un supernet. Création de toutes les nouvelles données des téléchargements de fichiers ne fonctionnera pas de chevauchement de plages. Si vous avez déjà chargé un fichier de construction, téléchargez le fichier en cours et le charger à nouveau pour identifier les chevauchements et résoudre le problème. Tout chevauchement dans les fichiers précédemment téléchargés peut entraîner les mappages incorrects de sous-réseaux et bâtiments dans les rapports. 


#### <a name="vpn"></a>VPN

La qualité d’expérience (QoE) les données clients envoient vers Office 365, qui est où sont issues des données CQD — inclut un indicateur VPN. Toutefois, cet indicateur s’appuie sur fournisseurs VPN signaler à Windows que l’adaptateur de réseau VPN enregistré est une carte d’accès à distance. Pas de tous les fournisseurs VPN enregistrement correctement les cartes d’accès à distance. De ce fait, vous est peut-être pas en mesure d’utiliser les filtres de requête VPN intégrés. Il existe deux approches pour les sous-réseaux VPN dans le bâtiment fichier d’informations.

-   Définir un **Nom de réseau** en utilisant le texte « VPN » dans ce champ pour les sous-réseaux VPN.

![Capture d’écran d’un rapport dans l’appel tableau de bord qualité qui définit comment créer un sous-réseau VPN](media/quality-of-experience-review-guide-image10.png)

_Figure 10 - VPN à l’aide du nom de réseau_

-   Définissez un **Nom** à l’aide du texte « VPN » dans ce champ pour les sous-réseaux VPN.

![Capture d’écran d’un rapport dans l’appel tableau de bord qualité qui définit la procédure pour créer une définition de construction constituant un sous-réseau VPN.](media/quality-of-experience-review-guide-image11.png)

_Figure 11 : VPN à l’aide du nom de construction_

> [!IMPORTANT]
> Certaines implémentations VPN ne signalent pas correctement les informations de sous-réseau. Si cela se produit dans votre rapport, qu'il est recommandé que lorsque vous ajoutez un sous-réseau VPN à la création du fichier, au lieu d’une entrée pour le sous-réseau, vous pouvez ajouter des entrées distinctes pour chaque adresse dans le sous-réseau VPN comme un réseau distinct de 32 bits. Chaque ligne peut comporter les mêmes métadonnées de construction. Par exemple, au lieu d’une seule ligne de 172.16.18.0/24 vous avez 253 lignes, avec une ligne pour chaque adresse de 172.16.18.1/32 à 172.16.18.254/32, inclus.


> [!NOTE]
> Connexions VPN ont été identifiées mal identifier la connexion réseau comme filaire lors de la connexion internet sous-jacent est sans fil. Lorsque vous examinez la qualité sur les connexions VPN, vous ne pouvez pas supposer que le type de connexion a été correctement identifié.

### <a name="uploading-building-information"></a>Chargement des informations de génération

Le tableau de bord des rapports de synthèse de CQD inclut une page **De téléchargement de données client** , accédée en sélectionnant la balise de lien **De téléchargement de données client** dans le coin supérieur droit (recherchez l’icône engrenage). Cette page est utilisée pour les administrateurs de télécharger leurs propres informations, par exemple le mappage d’adresse IP et les informations géographiques, mappage de chaque point d’accès sans fil et son adresse MAC et ainsi de suite.

1.  Accédez à CQD en ligne en accédant à <https://cqd.lync.com>.

2.  Sélectionnez l’icône ENGRENAGE dans le coin supérieur droit et choisissez **Clients du téléchargement des données** à partir de la page de **Rapports de synthèse** .

![Capture d’écran d’une boîte de dialogue du tableau de bord qualité appeler s’affiche pendant le téléchargement des données.](media/quality-of-experience-review-guide-image12.png)

_Figure 12 : menu de téléchargement des données clients_

1.  Ou bien, s’il s’agit de votre première visite CQD, vous devez télécharger les données de construction. Vous pouvez sélectionner **Télécharger maintenant** pour accéder rapidement à la page **De téléchargement de données client** .

![Capture d’écran d’une bannière dans l’appel tableau de bord qualité qui avertit l’utilisateur de télécharger des données de construction.](media/quality-of-experience-review-guide-image13.png)

_Figure 13 : création de bannière de téléchargement de données_

1.  Sur la page **De téléchargement de données client** , sélectionnez **Parcourir** pour choisir un fichier de données.

2.  Après avoir sélectionné un fichier de données, spécifiez la **date de début** et, le cas échéant, spécifiez une date de fin.

3.  Après avoir sélectionné la **date de début**, sélectionnez **Télécharger** pour télécharger le fichier pour le CQD. <br><br>Avant que le fichier est téléchargé, il est validé. Si la validation échoue, un message d’erreur s’affiche demandant de corriger le fichier. La figure suivante illustre une erreur ne se produise lorsque le nombre de colonnes dans le fichier de données est incorrect.

![Capture d’écran d’une boîte de dialogue dans l’appel tableau de bord qualité qui décrit un message d’erreur lors de l’importation des données de construction.](media/quality-of-experience-review-guide-image14.png)

_Figure 14 : erreur de chargement de données de création_

4.  Si aucune erreur ne se produit lors de la validation, le téléchargement du fichier réussit. Vous pouvez voir le fichier de données téléchargées dans la table **Mes téléchargements** , qui affiche la liste complète de tous les fichiers téléchargés pour les clients en cours au bas de cette page.

> [!NOTE]
> Il peut prendre jusqu'à quatre heures pour terminer le traitement de la création du fichier. <br><br> Si vous avez déjà téléchargée de création du fichier et pour ajouter les sous-réseaux qui peuvent ont été omis ou exclus, modifier le fichier d’origine en ajoutant les nouveaux sous-réseaux, supprimez le fichier actuel et téléchargez à nouveau le fichier qui vient d’être modifié. Il peut y avoir qu’un seul bâtiment actif CQD de fichier de données. 

### <a name="missing-subnets"></a>Sous-réseaux manquants

Après le téléchargement des informations de génération pour les réseaux gérés, chaque réseau géré doit avoir une association de construction. Toutefois, ce n’est pas toujours le cas ; en général, plusieurs sous-réseaux sont ignorés. Cette section explique comment valider ces réseaux manquant.

Accédez à la page **Rapports détaillés** dans CQD en ligne et accédez à l' **État de sous-réseau manquant** inclus dans les modèles CQD. Cela présente tous les sous-réseaux avec les flux de 10 ou plus audio qui ne sont pas définis dans le bâtiment du fichier de données. Assurez-vous qu’il n’y a aucun réseau géré dans cette liste. Si des sous-réseaux sont manquants, mettre à jour le bâtiment d’origine du fichier de données et recharger ce dernier à CQD.

> [!IMPORTANT]
> Vous devez ajouter votre ID de client comme un filtre de requête pour le **Second ID de clients** à ce rapport à filtrer le rapport pour afficher uniquement les données de clients de votre organisation. Dans le cas contraire, le rapport affichera des sous-réseaux fédérés.

> [!NOTE] 
> Veillez à régler le filtre de rapport année du mois pour le mois en cours. Sélectionnez **Modifier**et régler le filtre de rapport **Mois année** pour enregistrer le nouveau mois par défaut.                                                  |

![Rapport montrant des sous-réseaux non inclus dans le fichier de données de création de CQD afficher l’utilisation.](media/quality-of-experience-review-guide-image15.png)

_Figure 15 : manquante état de construction_

## <a name="reliability-investigations"></a>Enquêtes de fiabilité

La première étape de l’amélioration de la qualité est d’évaluer l’état de fiabilité audio au sein de l’organisation. Dans la mesure où la fiabilité audio est essentielle pour une expérience utilisateur positive, nous allons commencer avec les deux composants qui mesurent la fiabilité :

1.  **Appeler les échecs d’installation :** Session n’a pas pu être établie.

2.  **Appels infructueux de dépôt :** Session a été établie et est interrompue de manière inattendue

Dans cette section, nous présenterons des méthodes pour étudier les deux zones.

> [!NOTE]
> Pas de tous les rapports inclus dans les modèles sont abordés dans ce guide. Reportez-vous à la description du rapport individuel pour plus d’informations.


### <a name="call-setup"></a>Appelez le programme d’installation

La priorité des erreurs appel appropriées dans ce domaine tout d’abord, parce que ces défaillances ont un impact négatif sur l’expérience de l’utilisateur.

Commencer votre investigation en évaluant le pourcentage d’échecs d’installation appel globale de l’organisation et classer les zones d’enquête basée sur le pourcentage le plus élevé par bâtiment ou par réseau.

#### <a name="call-setup-failures-overall"></a>Appeler les échecs d’installation générales

Ce rapport de graphique affiche le montant total d’appel réussi, définir et appeler les échecs d’installation dans le temps. Pointez sur l’une des colonnes pour afficher les valeurs individuelles, comme illustré dans la figure ci-dessous.

![Capture d’écran d’un graphique qui affiche le pourcentage des données Audio appeler flux Échec de l’installation](media/quality-of-experience-review-guide-image16.png)

_Échecs d’installation de la figure 16 - fiabilité Audio - appel de flux_

##### <a name="analysis"></a>Analyse

Ce rapport affiche l’utilisation de paramètres d’appel audio et les pannes de votre organisation dans le temps. À l’aide de ce rapport, vous pouvez répondre aux questions suivantes et déterminer votre cours d’action suivant :

1.  Quel est le pourcentage d’échec d’installation appel total pour le mois en cours ?

2.  Est le pourcentage d’échec total appel d’installation au-dessous ou au-dessus de la mesure de la cible défini ?

3.  La tendance à l’échec n’est pire ou la meilleure que le mois précédent ?

4.  La tendance à l’échec augmente, steady, ou diminue ?

Les informations présentées dans ce rapport indique le récit de la fréquence à laquelle vos paramétrages d’appel globale ne sont pas au sein de votre organisation.

Indépendamment des réponses précédentes, prendre le temps d’étudier plus en utilisant les sous-rapports inclus pour rechercher n’importe quel des bâtiments ou des réseaux nécessitant des mesures correctives. Bien que le taux d’échec global sous la métrique de la cible, souvent le taux d’échec pour une ou plusieurs des bâtiments ou des réseaux se situent au-dessus de la mesure et ont besoin de mise à jour.

#### <a name="call-setup-failures-by-building-and-subnet"></a>Appeler les échecs d’installation en créant et en sous-réseau 

Ce rapport de tableau est utilisé pour détecter et isoler les bâtiments ou les réseaux auxquels il faut remédier.

> [!NOTE]
> Veillez à régler le filtre de rapport année du mois pour le mois en cours. Sélectionnez **Modifier**et régler le filtre de rapport **Mois année** pour enregistrer le nouveau mois par défaut.


![Signaler que les causes d’erreurs d’installation listes d’appel, organisées par construction, le réseau et sous-réseau par mois.](media/quality-of-experience-review-guide-image17.png)

_Figure 17 - échecs d’installation Audio en créant ou sous-réseau_

##### <a name="remediation"></a>Mise à jour 

Concentrer vos efforts de correction sur les bâtiments ou les sous-réseaux dont le plus grand volume d’échecs tout d’abord, parce que cela optimiser l’impact sur l’expérience utilisateur et aider à réduire rapidement les échecs d’installation d’organisation d’appel.
Le tableau suivant répertorie les deux raisons pour les échecs d’installation d’appel tel qu’indiqué par CQD.

_Le tableau 6 – raisons pour les échecs d’installation des appels_

| Appelez la raison des échecs d’installation                       | Causes courantes                                                                                                                                                                                                                                                                                   |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Manquant FW la règle d’Exemption de l’Inspection approfondie des paquets | Indique que le long du tracé, les équipements de réseau a empêché le chemin multimédia établie en raison des règles d’inspection approfondie des paquets. Cela est probablement dû à des règles de pare-feu n’est pas configurés correctement. Dans ce cas la négociation TCP a réussi, mais la négociation SSL n’a pas.               |
| Règle d’Exception FW IP bloc de manquant               | Indique que le long du tracé, les équipements de réseau a empêché le chemin multimédia établie au réseau Office 365. Peut-être en raison de règles de proxy ou de pare-feu n’est pas correctement configurés pour autoriser l’accès à des adresses IP et les ports utilisés pour les équipes et Skype pour le trafic de l’entreprise. |

Maintenant lorsque vous commencez votre mise à jour, vous pouvez concentrer vos efforts sur un immeuble particulier ou d’un sous-réseau. Comme indiqué dans le tableau précédent, ces problèmes sont dues à des configurations de pare-feu ou de proxy. Vérifiez les options dans le tableau suivant pour les actions de mise à jour.

_Tableau 7 : les étapes suivantes pour l’appel d’installation Échec de la conversion_

| Mise à jour           | Conseils     |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configurer l’ou les pare-feu | En collaboration avec votre équipe réseau et vérifiez votre configuration ou les pare-feu par rapport à [la liste d’adresses Office 365 IP](https://aka.ms/o365ips). Vérifiez que les ports et les [sous-réseaux de support](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) sont inclus dans les règles de pare-feu. Vérifiez que les ports TCP et UDP sont ouverts dans le pare-feu. Support préfère UDP TCP. TCP est considéré comme un protocole de retour arrière.<br><ul><li>**TCP :** le port 443</li><li>**UDP :** ports 3478 – 3481</li><ul> |
| Vérifier                | Tirer parti de l' [Outil d’évaluation réseau Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) pour vérifier la connectivité à partir du bâtiment concerné ou d’un sous-réseau à l’aide de la fonction de vérification de connectivité.    |


### <a name="call-drop"></a>Liste d’appels

À la différence des échecs d’installation des appels, est aucun code motif pour indiquer pourquoi appel abandonné les échecs s’est produite, qui le rend difficile à isoler une cause spécifique. Pour mieux trier les appels abandonnés, utilisez une approche déduite. Par corriger toutes les zones d’intérêt pour l’audio, correction des clients et l’utilisation de périphériques certifiés de conduite pour les équipes et Skype pour les entreprises, vous attendez des échecs d’appel abandonné à refuser.

#### <a name="call-drop-failures-overall"></a>Appeler des échecs de dépôt globale

Ce rapport graphique affiche le montant total de flux de données audio, des flux de données audio total déposé, et flux total déposé le pourcentage. Pointez sur l’une des colonnes pour afficher ses valeurs, comme illustré dans la figure suivante.

![Capture d’écran d’un graphique indiquant le pourcentage de suppression de flux appel Audio](media/quality-of-experience-review-guide-image18.png)

_Pourcentage d’échec figure 18 - appel Total supprimée_

##### <a name="analysis"></a>Analyse

Ce rapport graphique affiche l’utilisation et les pannes de votre organisation dans le temps relatifs à appeler les gouttes. À l’aide de ce rapport, vous pouvez répondre aux questions suivantes :

1.  Quel est l’appel de total en cours de suppression pourcentage ?

2.  Est le pourcentage de dépôt total sous la métrique cible définie ?

3.  La tendance à l’échec n’est pire ou la meilleure que le mois précédent ?

4.  La tendance à l’échec augmente, steady, ou diminue ?

Les informations présentées dans ce rapport peuvent indiquer l’histoire de la fréquence à laquelle vos gouttes d’appel globale sont produisent au sein de votre organisation.

Indépendamment des réponses aux questions ci-dessus, prenez le temps d’étudier en utilisant les sous-rapports pour rechercher les bâtiments ou les réseaux nécessitant des mesures correctives. Bien que le taux global de la liste ci-dessous la métrique cible, souvent le taux pour une ou plusieurs des bâtiments ou des réseaux est au-dessus de la mesure et doit être mise à jour.

#### <a name="call-drop-failures-by-building-or-subnet"></a>Appeler des échecs de dépôt par bâtiment ou par sous-réseau

Échecs dans ce rapport de tableau indiquent que l’appel a été abandonné de manière inattendue et a abouti à une expérience négative de l’utilisateur. Il y a deux rapports de tableau inclus dans le modèle, d’étude de conférence et l’autre pour les deux tiers.

> [!NOTE]
> Veillez à régler le filtre de l’année du mois pour le mois en cours. Sélectionnez **Modifier**, puis modifiez les **Mois année** pour enregistrer le nouveau mois par défaut.


![État qui répertorie le nombre et le pourcentage de suppression appels, organisées par construction, le réseau et sous-réseau par mois.](media/quality-of-experience-review-guide-image19.png)

_Figure 19 – appel de Audio supprimée les échecs par bâtiment ou par sous-réseau_

##### <a name="remediation"></a>Mise à jour

À l’aide de l’état précédent de la table, vous pouvez désormais isoler les « hot spots » dans le réseau géré où se produisent les gouttes d’appel au-dessus de la mesure de la cible défini. Concentrer vos efforts de correction sur les bâtiments ou les réseaux ayant le nombre le plus élevé de flux total tout d’abord, pour avoir un impact considérable.

Causes courantes de gouttes d’appel :

-   Sortie de réseau ou à internet dans-mis en service

-   Aucune fonction QoS est configurée sur les réseaux de contraintes

-   Versions antérieures du client

-   Comportement de l’utilisateur

Une fois que vous découvrez des zones réactives, vous pouvez exploiter [Analytique d’appeler](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309) pour un examen plus approfondi utilisateurs dans cette construction de problèmes spécifiques. Analytique d’appel contient les données d’identification personnelle et peut être utile pour isoler davantage les raisons potentielles pour les gouttes d’appel.

Quel que soit l’étape suivante, il est conseillé d’avertir le support technique qu’un problème a été découvert avec les bâtiments spécifiques ou de sous-réseaux. De cette façon, ils peuvent rapidement répondre aux appels entrants et trier les utilisateurs plus efficacement. Les utilisateurs avec indicateur peuvent ensuite être renvoyées à l’équipe technique pour examen ultérieur.

Le tableau suivant répertorie des méthodes communes pour gérer et résoudre les gouttes d’appel.

_Tableau 9 : les étapes suivantes pour l’appel drop mise à jour_

| Mise à jour                              | Conseils     |
|------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Réseau/internet                         | Maintenant que vous savez quel immeuble est affecté, travailler avec votre équipe de réseau pour surveiller la bande passante au niveau création pour déterminer s’il existe des problèmes liés à l’utilisation abusive. Si le problème est découvert doit être associée à la congestion du réseau, pensez à plus de bande passante à la création. <br><br>**Qualité de service :** Si l’augmentation de la bande passante est impossible ou coût prohibitif, envisagez l’implémentation de QoS. Cela garantira que paquets multimédia sur le réseau géré sont classés par priorité au-dessus de trafic non-multimédia. Ou bien, s’il n’existe aucun élément de preuve claire que la bande passante est la cause du problème, tenez compte de ces solutions :<br><ul><li>[Conseils de qualité de service aux équipes de Microsoft](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)</li><li>[Skype pour obtenir des conseils professionnels QoS](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul><br>**Effectuer une évaluation de la disponibilité du réseau :** Une évaluation réseau fournit des détails sur l’utilisation de la bande passante attendu, comment faire face à la bande passante et du réseau change, mise en réseau de pratiques recommandées pour les équipes et Skype pour les entreprises. À l’aide de la table précédente comme source de, vous disposez d’une liste des bâtiments ou des sous-réseaux qui constituent d’excellents candidats pour une évaluation. <br><ul><li>[Évaluation de la préparation du réseau les équipes Microsoft](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#test-the-network)</li><li>[Skype pour évaluation de disponibilité du réseau de l’entreprise](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Outil d’évaluation réseau Microsoft :** Utilisez cet outil pour un simple test des performances du réseau pour déterminer comment le réseau effectue une équipes ou Skype pour appel Business Online. L’outil vous aide à évaluer les performances d’un sous-réseau et valider la disponibilité du réseau par rapport à des [exigences](https://aka.ms/performancerequirements)de performances Microsoft.<ul><li>[Téléchargez l’outil d’évaluation réseau](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul>         |
| Clients (Skype pour les entreprises en ligne uniquement) | Certains clients plus anciens ont connu, documenté des problèmes avec la fiabilité des supports. Examiner les rapports Analytique d’appeler à partir de plusieurs utilisateurs affectés ou créer un rapport de tableau de Version de Client personnalisé dans CQD filtré pour bâtiments spécifiques ou de sous-réseaux avec mesure de % Total appeler supprimé une défaillance. Ces informations vous aideront à comprendre si une relation existe entre gouttes d’appel dans cette construction spécifique et une version spécifique du client.                                                                                                                                                              |
| Périphériques                                  | La plupart des défaillances du périphérique sont dus à l’utilisation de périphériques qui ne sont pas certifiés pour les équipes ou Skype pour les entreprises. Échecs prennent généralement la forme de haut-parleurs intégrés ou de micros qui sont utilisés ou de combinaisons du écouteur/mic qui sont branchés dans la prise jack audio de 3,5 mm sur un périphérique. Recommandation la plus courante de Microsoft est que tous les utilisateurs qui rencontrent appellent gouttes — ou médiocre appelle en général — et sont à l’aide de dispositifs intégrés ou les pilotes doit être mis en service d’un [certified casque ou haut-parleur](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). |
| Comportement de l’utilisateur                            | Si vous déterminez que le réseau, périphériques ni les clients sont le problème, envisagez d’engager [Mes Advisor](https://aka.ms/myadvisor) pour des instructions sur le développement d’une stratégie d’adoption utilisateur pour apprendre aux utilisateurs comment mieux la jointure et quitter les réunions. Une équipes les plus intelligentes et Skype utilisateur produira une meilleure expérience utilisateur pour tous les participants à la réunion. Un utilisateur qui met leur ordinateur portable en veille (en refermant le couvercle) sans quitter la réunion est considéré comme une cible d’appel inattendu.     |

## <a name="quality-investigations"></a>Enquêtes de qualité

L’étape suivante pour évaluer l’état de qualité audio lors du déploiement consiste à étudier Audio médiocre appeler Ratio (PCR), TCP et l’utilisation du proxy. Il est important de se rappeler que les données CQD ne vous fournissent pas une cause principale spécifique, mais fournit à la place des problématiques susceptibles de commencer une conversation de collaboration avec les équipes appropriés pour les activités de mise à jour.

> [!NOTE]
> Pas de tous les rapports inclus dans les modèles sont abordés dans ce guide. Reportez-vous à la description du rapport individuel pour plus d’informations. 


### <a name="investigate-call-quality"></a>Examiner la qualité des appels

Le pourcentage global de la PCR est principalement utilisé pour indiquer si l’organisation est objectifs définis audio métrique. Il est important de noter que même si le pourcentage global de cible, certains sous-réseaux ou des bâtiments ne peuvent pas atteindre les objectifs définis et donc une analyse plus poussée. Par exemple, si le pourcentage PCR audio d’organisation est de 3 pour cent en décembre, qui répond à la cible de l’échantillon, les bâtiments spécifiques peut-être toujours des mauvaises expériences, en fonction de la distribution de ce % 3.

#### <a name="overall-organizational-poor-call-percentage"></a>Ensemble d’organisation appel faible pourcentage

Pour évaluer le pourcentage global des appels médiocres de l’organisation utilisent le rapport de graphique de qualité globale.

![Capture d’écran d’un graphique indiquant le pourcentage d’appels de mauvaise qualité](media/quality-of-experience-review-guide-image20.png)

_Figure 20 – qualité Audio - général_

##### <a name="investigation"></a>Enquête

Ce graphique affiche l’utilisation et la PCR de votre organisation au fil du temps. À l’aide de ce rapport, vous pouvez répondre aux questions suivantes :

1.  Quelle est la PCR totale pour le mois en cours ?

2.  Voici la PCR la métrique cible définie ?

3.  La tendance à l’échec n’est pire ou la meilleure que le mois précédent ?

4.  La tendance à l’échec augmente, steady, ou diminue ?

Indépendamment des réponses aux questions ci-dessus, prenez le temps d’étudier en utilisant les sous-rapports à rechercher pour les bâtiments ou les réseaux qui peuvent nécessitent une étude approfondie. Bien que la PCR globale sous la métrique de la cible, souvent la PCR pour un ou plusieurs des bâtiments ou des réseaux est supérieure à la mesure et a davantage besoin d’enquête.

#### <a name="audio-quality-overall"></a>Audio qualité globale

Il existe deux arborescences de rapport inclus dans les modèles de qualité audio, pour étudier les conférences et l’autre pour les appels de deux tiers. Aux fins de la réparation de la qualité, le processus d’investigation étant les mêmes, nous allons nous concentrer ici sur la conférence. Amélioration de la qualité de conférence affectera également positivement qualité de l’appel de deux tiers. Les rapports sont également inclus pour afficher une qualité audio de la conférence et deux tiers en filaire et le Wi-Fi.

> [!NOTE]
> Examen des deux tiers des appels médiocres est similaire à l’analyse des téléconférences. La tâche est d’identifier les bâtiments ou les sous-réseaux ayant la qualité la plus faible pour vérifier si il existe un modèle d’appels médiocres avec un autre bâtiment ou sous-réseau. 

![Capture d’écran de la qualité Audio - rapport de conférence dans le tableau de bord qualité appeler.](media/quality-of-experience-review-guide-image21.png)

_Figure 21 – qualité Audio - conférence_

##### <a name="investigation"></a>Enquête

Ce rapport de graphique affiche la conférence ou de l’utilisation de deux tiers et PCR de votre organisation dans le temps. À l’aide de ce rapport, vous pouvez répondre aux questions suivantes :

1.  Quelle est la PCR totale pour le mois en cours ?

2.  Voici la PCR la métrique cible définie ?

3.  PCR n’est pire ou la meilleure que le mois précédent ?

4.  La tendance de la PCR augmente, steady, ou diminue ?

Indépendamment des réponses aux questions ci-dessus, prenez le temps d’étudier en utilisant les sous-rapports à rechercher pour les bâtiments ou les réseaux peuvent être examinés. Bien que la PCR globale sous la métrique de la cible, souvent la PCR pour un ou plusieurs des bâtiments ou des réseaux est au-dessus de la mesure et doit être mise à jour.

#### <a name="poor-audio-stream-by-building-and-subnet"></a>Flux de données audio médiocre en créant et en sous-réseau

Ce rapport de tableau vous donne des informations supplémentaires sur ce qui a contribué à appels sont classées comme médiocres et vous aide à isoler les zones réactives du réseau géré.

Fait la distinction entre les détails de connexion filaire et le Wi-Fi et inclut la gigue, perte de paquets et les mesures de temps d’aller-retour (RTT). Un rapport similaire existe dans les rapports de deux tiers et est utilisé pour isoler des deux tiers des appels sur votre réseau géré.

> [!NOTE]
> Veillez à régler le filtre de l’année du mois pour le mois en cours. Sélectionnez **Modifier**, puis modifiez les **Mois année** pour enregistrer le nouveau mois par défaut. 

> [!TIP]
> Des réseaux domestiques sont difficiles à triage en raison de leur utilisation généralisée. Un rapport distinct qui utilise l’adresse IP du pare-feu a été ajouté au modèle de tous les réseaux pour vous aider à la correction des bureaux qui utilisent des réseaux.

![État qui répertorie les types de connexion, les types de transport et PCR supérieure à 3 %, ainsi que différents motifs de mauvaise qualité organisés par la génération, du réseau et sous-réseau par mois.](media/quality-of-experience-review-guide-image22.png)

_La figure 22 - résumé des flux de données Audio médiocre en créant - et le sous-réseau conférence_

##### <a name="remediation"></a>Mise à jour

Concentrer vos efforts de correction des bâtiments ou rencontrer rapidement des réseaux qui ont le plus grand volume de flux audio, car cette opération de maximiser l’impact et de contribuer à l’amélioration de l’utilisateur. Utilisez la gigue, perte de paquets et les mesures de temps RTT pour comprendre ce qui contribue à la qualité des appels médiocre. Il est possible d’avoir plusieurs problèmes :

-   **Variation :** Paquets de supports arrivent à des vitesses différentes, ce qui entraîne un haut-parleur à son robotique.

-   **Perte de paquets :** Paquets de supports sont en cours de suppression, qui crée l’effet de manquer des mots ou des syllabes.

-   **RTT :** Paquets de supports sont prend beaucoup de temps pour atteindre leur destination, ce qui crée un effet de talkie-walkie.

Bien qu’aucune source unique de vérité des comptes pour ce qui peut provoquer un appel médiocre, plusieurs méthodes courantes peuvent vous aider à traiter les anomalies du réseau.

Pour aider votre enquête sur les problèmes de qualité, vous pouvez exploiter [Analytique d’appeler](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309).
Avec appel Analytique, vous pouvez consulter une conférence spécifique ou de l’état d’appel détaillées des utilisateurs. Ce rapport contient les données d’identification personnelle et est utile lorsque vous tentez de discerner la raison des échecs. Une fois que vous savez quelle génération qui est affecté, suivi des utilisateurs dans cette construction doit être simple.

N’oubliez pas d’informer le service d’assistance que ces réseaux est confrontés à des problèmes de qualité, afin de trier rapidement et répondre aux appels entrants.

_Le tableau 9 - communs contributeurs à haute PCR_

| Mise à jour                              | Conseils       |
|------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Réseaux                                 | Un réseau surexploité peut manifester ou configuré sous peut provoquer des problèmes de qualité du média. Travail avec l’équipe réseau afin de déterminer si les connexions réseau de l’utilisateur à la sortie d’internet pointent a bande passante suffisante pour prendre en charge les supports. **Effectuer une évaluation de la disponibilité du réseau :** Une évaluation réseau fournit des détails sur l’utilisation de la bande passante attendu, comment faire face à la bande passante et du réseau change, mise en réseau de pratiques recommandées pour les équipes et Skype pour les entreprises. À l’aide de la table précédente comme source de, vous disposez d’une liste des bâtiments ou des sous-réseaux qui constituent d’excellents candidats pour une évaluation.<br><ul><li>[Évaluation de la préparation du réseau les équipes Microsoft](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#test-the-network)</li><li>[Skype pour évaluation de disponibilité du réseau de l’entreprise](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Outil d’évaluation réseau Microsoft :** Utilisez cet outil pour un simple test des performances du réseau pour déterminer comment le réseau effectue une équipes ou Skype pour appel Business Online. Cet outil vous permet d’évaluer la performance d’un sous-réseau et valider la disponibilité du réseau contre les performances de Microsoft [exigences](https://aka.ms/performancerequirements).<br><ul><li>[Téléchargez l’outil d’évaluation réseau](https://www.microsoft.com/download/details.aspx?id=53885) </li></ul>        |
| Qualité de Service (QoS)                 | QoS est une méthode éprouvée pour aider à hiérarchiser les paquets sur un réseau pour vous assurer qu’elles arrivent à leur destination intacte et dans les temps. Envisagez l’implémentation de QoS de votre organisation afin d’optimiser la qualité de l’expérience de l’utilisateur où la bande passante est limitée ou contrainte. QoS vous aideront à résoudre les problèmes généralement associés à des niveaux élevés de perte de paquets, et, à un degré moindre, temps de gigue et aller-retour. <br><ul><li>[Conseils de qualité de service aux équipes de Microsoft](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)</li><li>[Skype pour obtenir des conseils professionnels QoS](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul>    |
| Wi-Fi                                    | Wi-Fi peut avoir un impact significatif sur la qualité des appels. Conception de Wi-Fi ne prendre généralement en considération la configuration réseau requise pour les services VoIP et constituent souvent une source de mauvaise qualité. **Qualité de service :** Les réseaux sans fil modernes doivent prendre en charge de nombreux périphériques. Ces périphériques sont en concurrence pour la bande passante et peuvent entraîner des problèmes de qualité pour les services VoIP où la vitesse et la latence sont essentielles. Consultez votre fournisseur sans fil pour les caractéristiques de l’objet et implémentez la QoS sur votre réseau sans fil pour définir la priorité pour les professionnels et les équipes de support Skype. **Densité de point d’accès :** Points d’accès (AP) peuvent être trop éloignés ou pas dans un emplacement idéal. Pour réduire l’interférence potentielle, placez des points d’accès supplémentaires dans les salles de conférence et dans les emplacements qui ne sont pas obstruées par parois ou d’autres objets. **2,4 GHz et 5 GHz :** 5 GHz fournit moins interférence d’arrière-plan et des vitesses plus élevées et doivent être prioritaires lors du déploiement VoIP via le Wi-Fi. Toutefois, 5 GHz n’est pas aussi forte que 2,4 GHz et ne traversent les murs aussi facilement. Examinez votre plan de bâtiment pour déterminer quelle fréquence vous pouvez vous fier pour la meilleure connexion. **Force du signal :** Traditionnellement, exprimée en dBm (rapport de puissance en décibels), ce compteur mesure l’intensité du signal sans fil. Après avoir connecté un périphérique à un point d’accès, il ne souhaite pas laisser accéder facilement. Lorsque le périphérique s’éloigne du point d’accès, l’intensité du signal tombe à un point qui induit une connexion de qualité médiocre, même si le point d’accès d’un autre, plus proche n’est disponible. Si possible, contactez votre fournisseur de point d’accès pour vous assurer que les points d’accès sont configurés pour supprimer un périphérique lorsque l’intensité du signal tombe au-dessous d’un niveau acceptable. Cela garantit que le périphérique ne se bloque pas un point d’accès faibles. C’est une bonne solution lorsque vous ne pouvez pas facilement ajouter plus de points d’accès. **Pilote sans fil :** Lorsque tout le reste échoue, assurez-vous que les pilotes sans fil sont à jour. Cela permet d’atténuer une expérience utilisateur médiocre lié à un pilote obsolète. |
| Dispositif de réseau                           | Les grandes entreprises peut-être des centaines de périphériques répartis sur le réseau. Travail avec votre équipe réseau afin de garantir les périphériques réseau de l’utilisateur à internet sont gérées et à jour.     |
| VPN                                      | Il a été très bien documenté que les appareils VPN ne sont pas traditionnellement conçus pour gérer des charges de travail multimédia en temps réel. Certaines configurations VPN interdisent l’utilisation d’UDP (qui est le protocole par défaut pour l’audio) et s’appuient sur TCP uniquement. Envisagez d’implémenter une [solution de fractionnement-tunnel VPN](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) afin de réduire les VPN en tant que source de mauvaise qualité.        |
| Clients (Skype pour les entreprises en ligne uniquement) | Les anciens clients sont connus pour provoquer des problèmes avec le support. S’assurer que les clients sont patchés dans les six mois à compter de la publication. Exploiter [MyAdvisor](https://aka.ms/myadvisor) pour obtenir des conseils sur le développement d’une stratégie de disponibilité du client et déployer [Clic](https://technet.microsoft.com/library/jj219427.aspx).      |
| Périphériques                                  | L’utilisation de [optimisé de périphériques](https://partnersolutions.skypeforbusiness.com/solutionscatalog) peut aider à améliorer de manière significative l’expérience utilisateur. Avec toutes les choses étant égales, les périphériques optimisés sont conçus pour optimiser l’expérience utilisateur avec des équipes et Skype pour les entreprises et produire une qualité supérieure. Utiliser [MyAdvisor](https://aka.ms/myadvisor) pour obtenir des conseils sur le développement d’une stratégie de disponibilité du périphérique.   |


### <a name="investigate-tcp-audio-sessions"></a>Vérifier les sessions TCP audio

TCP est considéré comme un transport de retour arrière et pas le transport principal que vous souhaitez pour le multimédia en temps réel. Il s’agit d’un transport de restauration automatique fait en raison de la nature dynamique du protocole TCP. Par exemple, si un appel est effectué sur un réseau latent et paquets media sont retardées, puis les paquets à partir d’il y a quelques secondes, qui ne sont plus utiles, sont en concurrence pour la bande passante atteindre le destinataire, ce qui peut aggraver une mauvaise situation. Cela rend le cheval de guérisseur audio et étirement audio, ce qui entraîne des bruits audibles souvent sous la forme d’une gigue.

Les rapports de cette section ne faire une distinction entre les appels de bonnes et de mauvaises. Étant donné qu’UDP est préféré, le rapports recherchez l’utilisation de TCP pour l’audio. Cela est dû principalement par des règles de pare-feu incomplète. Pour plus d’informations sur les règles de pare-feu pour les équipes et Skype pour professionnels en ligne, consultez [Office 365 URL et les plages d’adresses IP](https://aka.ms/o365ips).

> [!IMPORTANT]
> Ayant un valide [Création fichier](#building-mapping) téléchargé est recommandé pour être en mesure de distinguer rapidement à l’intérieur de flux de données audio externe lorsque vous examinez l’utilisation TCP. 


#### <a name="audio-streams-with-tcp-usage-overall"></a>Flux de données audio avec l’utilisation TCP globale

Ce rapport indique l’utilisation globale de TCP pour les données audio sur les sept derniers mois, comme illustré ci-dessous.

Tous les autres rapports de cette section seront concentre sur cerner les bâtiments spécifiques et les sous-réseaux où TCP est la plus couramment utilisée. Sous-rapports plus décomposer l’utilisation TCP par les conférences et les appels de deux tiers.

![Capture d’écran d’un graphique indiquant le nombre de flux de données audio TCP par mois](media/quality-of-experience-review-guide-image23.png)

_Figure 23 – les flux Audio avec l’utilisation TCP_

##### <a name="investigation"></a>Enquête

Ce graphique affiche l’utilisation TCP globale de votre organisation. À l’aide de ce rapport, vous pouvez répondre aux questions suivantes :

1.  Quel est le volume total des appels TCP pour le mois en cours ?

2.  Est-ce moins bonne ou meilleure que le mois précédent ?

3.  L’évolution de l’utilisation TCP augmente, steady, ou diminue ?

Si vous remarquez l’augmentation de l’évolution de l’utilisation TCP ou au-dessus de l’utilisation normale du mensuelle, prenez le temps d’étudier en utilisant les sous-rapports pour rechercher les bâtiments ou les réseaux nécessitant des mesures correctives. Dans l’idéal, vous souhaitez que des sessions audio basés sur TCP aussi peu que possible sur le réseau géré.

#### <a name="tcp-vs-udp"></a>TCP et UDP

Ce rapport de tableau identifie le volume du protocole TCP et UDP rapport d’utilisation sur le dernier mois pour les conférences audio, vidéo et vidéo écran partage (VBSS).

![Rapport affichant le volume de TCP par rapport au flux de données UDP conférence, avec PCR indiqué pour la comparaison](media/quality-of-experience-review-guide-image24.png)

_Figure 24 – TCP et UDP - conférence_

##### <a name="analysis"></a>Analyse

Même si vous souhaitez une utilisation TCP pour être aussi faible que possible, vous verrez peut-être un peu de l’utilisation TCP dans un déploiement correct dans le cas contraire. Pour comparer l’utilisation TCP UDP, divisez le flux de données audio TCP par flux de données audio UDP pour déterminer un pourcentage. Une valeur supérieure à 1 % doit être approfondie.

Dans l’exemple ci-dessus, nous prenons des flux de données TCP 1,806 divisé par 10,481 flux UDP d’arriver à une valeur de 17,2 %. Cette valeur est nettement supérieur à 1 % et nous indique que nous devons continuer nos recherches afin de déterminer où se produit l’utilisation TCP.

Également inclus dans le rapport est pourcentage faible d’Audio. Cela vous donne une vue de la comparaison de la qualité des appels entre UDP et TCP pour aider à visualiser comment TCP affecte la qualité de l’appel overcall.

Maintenant que vous avez déterminé qu’il y a une utilisation élevée de l’audio de type TCP dans votre organisation, que faire ensuite ? Consultez les rapports de **flux de données TCP en créant et en sous-réseau** pour décomposer l’utilisation TCP par construction et des sous-réseaux.

#### <a name="tcp-streams-by-building-and-subnet"></a>Flux de données TCP en créant et en sous-réseau

Dans les modèles CQD fournis, atteindre le flux de données TCP par sous-réseau et création de rapports de tableau à l’aide soit géré, soit tous les modèles de réseaux. Il existe trois états inclus dans le modèle, une pour étudier la conférence, avec et sans les informations de relais Microsoft et l’autre pour rechercher les appels de deux tiers. Aux fins de l’analyse de l’utilisation TCP, le processus est le même, donc nous allons nous concentrer sur la conférence seulement la discussion ici.

> [!IMPORTANT]
> Ayant un valide [Création fichier](#building-mapping) téléchargé est recommandé pour être en mesure de distinguer rapidement à l’intérieur de flux de données audio externe lorsque vous examinez l’utilisation TCP. 

> [!NOTE]
> Veillez à régler le filtre de l’année du mois pour le mois en cours. Sélectionnez **Modifier**, puis modifiez les **Mois année** pour enregistrer le nouveau mois par défaut.                                  |

![État qui répertorie les flux de données TCP, organisées par construction, le réseau et sous-réseau par mois.](media/quality-of-experience-review-guide-image25.png)

_Figure 25 – flux TCP en créant - et le sous-réseau conférence_

##### <a name="remediation"></a>Mise à jour

Ce rapport identifie les bâtiments spécifiques et les sous-réseaux sont contribuant au volume de l’utilisation TCP. Un rapport supplémentaire est également inclus pour identifier l’adresse IP relais de Microsoft qui a été utilisé dans l’appel pour aider à isoler les règles de pare-feu manquant. Concentrer vos efforts de correction de ces bâtiments qui ont le plus grand volume de flux audio afin d’optimiser l’impact.

La cause la plus courante de l’utilisation TCP n’a pas de règles d’exception de pare-feu ou proxy. Nous parle de proxy dans la section suivante, donc pour le moment concentrer vos efforts sur les pare-feu. À l’aide de la construction ou le sous-réseau fourni, vous pouvez déterminer celui qui doit être mis à jour.

_Tableau 10 - conversion * conseils pour les flux de données TCP en créant et en sous-réseau_

| Mise à jour        | Conseils     |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configurer le pare-feu | Vérifiez les [adresses et ports IP de 365 Office](https://aka.ms/o365ips) sont exclus de votre pare-feu. Bien qu’il existe de nombreuses adresses IP et les ports qui doivent être ouverts pour les problèmes de TCP relatifs aux médias, concentrer vos efforts d’initiales sur les points suivants : Vérifiez les suivants [des sous-réseaux de media](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) dans vos règles de pare-feu. Reportez-vous à la ligne 4 dans le tableau pour plus d’informations de sous-réseau de média spécifique. [Les ports UDP 3478 – 3481](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Updated-IP-ranges-and-ports-for-Skype-for-Business-Online/ba-p/47470): ces ports sont les ports du support de votre choix et doivent être ouvert, dans le cas contraire, le client est restauré sur le port TCP 443. |
| Vérifier             | Utilisez l' [Outil d’évaluation réseau Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) pour rechercher des problèmes de connectivité à Office 365 adressesIP et de ports spécifiques à partir du bâtiment concerné ou d’un sous-réseau.    |

### <a name="investigate-http-proxy-usage"></a>Étudier l’utilisation de proxy HTTP

Serveurs proxy HTTP ne sont pas le chemin d’accès par défaut pour l’établissement des sessions média, d’une multitude de raisons. La plupart contiennent des fonctionnalités d’inspection approfondie des paquets qui peuvent empêcher les connexions au service en cours d’exécution et introduire des interruptions de service. En outre, les proxy peut-être forcer TCP et ne pas autoriser UDP, ce qui est recommandé pour une qualité audio optimale.

Il est toujours de recommandation de Microsoft pour configurer le client pour se connecter directement à des équipes Skype pour les services. Ceci est particulièrement important pour le trafic multimédia.

> [!IMPORTANT]
> Ayant un valide [Création fichier](#building-mapping) téléchargé rend correctement distingue facilement à l’intérieur du flux de données audio externe lors de l’analyse de l’utilisation du proxy. 


#### <a name="audio-streams-with-http-proxy-usage-overall"></a>Flux de données audio avec l’utilisation du proxy HTTP globale

Ce rapport présente l’utilisation de proxy dans le temps sur une échelle mensuelle. L’état de flux de données HTTP proxy dans cette section du modèle est très similaire le rapports TCP. Il ne regarde si les appels sont faibles ou bon, mais si l’appel est connecté via HTTP.

![Capture d’écran des flux Audio avec le rapport de l’utilisation du Proxy HTTP dans le tableau de bord qualité appeler.](media/quality-of-experience-review-guide-image26.png)

_La figure 26 – les flux Audio avec l’utilisation du serveur Proxy HTTP_

##### <a name="analysis"></a>Analyse

Si vous voyez un volume élevé de l’utilisation HTTP, contactez votre équipe de mise en réseau pour vous assurer que les exclusions appropriées sont en place afin que les clients sont directement de routage pour les équipes ou Skype pour les sous-réseaux media Business Online. Dans l’idéal, il doit être sans l’utilisation HTTP affichée ici.

Si vous avez un seul proxy d’internet dans votre organisation, vérifiez le bon [Office 365 URL et les exclusions de plage d’adresses IP](https://aka.ms/o365ips). Si plus d’un proxy internet est configuré dans votre organisation, utilisez le protocole HTTP des rapports pour isoler le bâtiment ou sous-réseau est affecté.

Pour les organisations qui ne peuvent pas contourner le serveur proxy, vérifiez que le Skype pour client d’entreprise est configurée pour vous connecter correctement lorsqu’il se trouve derrière un serveur proxy comme décrit dans l’article [Skype pour entreprise doit utiliser le serveur proxy pour vous connecter au lieu d’essayer de direct connexion](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin).

#### <a name="http-proxy-streams-by-building-and-subnet"></a>Flux de données HTTP proxy en créant et en sous-réseau

Ce rapport identifie les bâtiments spécifiques et les sous-réseaux contribuant à l’utilisation HTTP.

> [!IMPORTANT]
> Ayant un valide [Création fichier](#building-mapping) téléchargé rend correctement distingue facilement à l’intérieur du flux de données audio externe lors de l’analyse de l’utilisation du proxy.

> [!NOTE]
> Veillez à régler le filtre de l’année du mois pour le mois en cours. Sélectionnez **Modifier**, puis modifiez les **Mois année** pour enregistrer le nouveau mois par défaut.                        |

![Capture d’écran de l’utilisation du Proxy HTTP par sous-réseau et création de rapport dans le tableau de bord qualité appeler.](media/quality-of-experience-review-guide-image27.png)

_Figure 27 – utilisation du Proxy HTTP en créant et sous-réseau_

##### <a name="remediation"></a>Mise à jour

Concentrer vos efforts de correction sur les bâtiments ou les sous-réseaux qui disposent de l’utilisation du proxy HTTP. La cause la plus courante de l’utilisation HTTP n’a pas de règles d’exception de proxy. À l’aide de la construction ou le sous-réseau fourni, vous pouvez déterminer quel proxy doit être mis à jour.

Vérifiez que le requis [Office 365 complets](https://aka.ms/o365ips) sont exclus de votre serveur proxy.

## <a name="endpoint-investigations"></a>Enquêtes de point de terminaison

Cette section se concentre sur les tâches de création de rapports sur Skype pour les versions de client d’entreprise spécifiques et l’utilisation de périphériques certifiés.

> [!NOTE]
> Pas de tous les rapports inclus dans les modèles sont abordés dans ce guide. Reportez-vous à la description du rapport individuel pour plus d’informations. 


### <a name="determine-client-versions"></a>Déterminer les versions de client

Le rapport dans cet espace se concentre sur l’identification de Skype pour les versions de client d’entreprise en cours d’utilisation et leur volume relatif dans l’environnement.

> [!IMPORTANT]
> Actuellement, les clients d’équipes sont distribués et mis à jour automatiquement par le biais de l’Azure réseau CDN (Content Delivery) et est maintenu à jour par le service. Préparation du client et des activités d’enquêtes ne sont pas applicables aux équipes.

Vous trouverez les numéros de version de Skype pour entreprise 2015 et 2016 via les liens ci-dessous :

-   [Versions de canal de mise à jour client Office 365](https://technet.microsoft.com/office/mt465751?f=255&MSPPError=-2147217396)

-   [Numéros de version et de build Office 365 pour cliquer pour exécuter](https://support.office.com/article/Version-and-build-numbers-of-update-channel-releases-ae942449-1fca-4484-898b-a933ea23def7)

-   [Skype pour les mises à jour et des téléchargements d’entreprise](https://technet.microsoft.com/office/dn788954.aspx)

> [!NOTE] 
> Veillez à régler le filtre de l’année du mois pour le mois en cours. Sélectionnez **Modifier**, puis modifiez les **Mois année** pour enregistrer le nouveau mois par défaut.  

> [!IMPORTANT]
> Rapports client vous obligent à exclure les données participants fédérées. Pour exclure les données participants fédérées, vous devez ajouter un filtre de requête pour **Second ID de clients** de votre organisation [d’ID de client](#tenant-id). |

![Capture d’écran de l’état Client et périphériques dans le tableau de bord qualité appeler.](media/quality-of-experience-review-guide-image28.png)

_Figure 28 - rapport de version de Client_

#### <a name="remediation"></a>Mise à jour

Une partie essentielle de la conduite des expériences utilisateur de qualité est de s’assurer que les clients managés sont exécutent des versions actualisées de Skype pour les entreprises. Cela offre plusieurs avantages, parmi lesquels :

-   Il est plus facile de gérer plusieurs versions par rapport aux versions antérieures.

-   Il fournit un niveau de cohérence de l’expérience.

-   Il facilite résoudre les problèmes liés à la qualité des appels et de la facilité d’utilisation.

-   Microsoft met continuellement optimisations et améliorations générales sur le produit. S’assurer que les utilisateurs reçoivent ces mises à jour réduit les risques de confronté à un problème qui a déjà été résolu.

Limitation de votre déploiement de versions de client qui sont âgés de moins de six mois pour améliorer l’expérience utilisateur globale et améliorer la gérabilité comparée à un grand nombre de versions différentes du client dans le même environnement.

Si vous utilisez uniquement Office-Démarrer en un clic, vous serez automatiquement dans la fenêtre de six mois. Aucune action supplémentaire n’est requise.

If, comme la plupart des entreprises, vous avez un mélange de packages-clic et le programme d’installation (MSI), vous pouvez utiliser le rapport pour vérifier que les clients MSI sont mis à jour régulièrement. Concentrer vos efforts sur ces clients où le volume est supérieur à la moyenne. Si vous remarquez de retard de clients, travailler avec l’équipe chargée de la gestion des mises à jour Office et vous assurer qu’ils vous l’approbation et le déploiement de correctifs client régulièrement.

### <a name="devices-investigations"></a>Enquêtes de périphériques

Pour utiliser de l’état de périphérique suivant, il est recommandé de comprendre le concept de l’avis de moyenne score (MOS). MOS a la mesure de gold standard pour évaluer la qualité audio. Elle est représentée sous la forme d’une note de nombre entier de 0 à 5.

La base de toutes les mesures de la qualité de la voix est la manière dont une personne perçoit la qualité de la reconnaissance vocale. Car il est affecté par la perception humaine, il est par nature subjectif. Il existe plusieurs méthodologies de test subjective.
La plupart des mesures de la qualité vocale sont basées sur une échelle d’évaluation (blocage) de catégorisation absolue.

Dans un test de subjective de blocage, un nombre statistiquement significatif de personnes évaluer leur qualité d’expérience sur une échelle de 1 (mauvais) à 5 (excellent). La moyenne des scores est le MOS. Le MOS qui en résulte dépend de la plage d’expériences qui ont été exposés pour le groupe et le type de l’expérience d’évaluation.

Parce qu’il est difficile d’effectuer des tests subjectives de la qualité de la voix pour un système de communication direct, équipes et Skype pour entreprise génèrent des valeurs de MOS à l’aide d’algorithmes avancés d’objectivement prédire les résultats d’un test subjectif.

Le jeu disponible de MOS et les attributs mesurables associés fournissent une vue de la qualité de l’expérience remis aux utilisateurs.

En fournissant aux utilisateurs des périphériques certifiés pour les équipes et Skype pour les entreprises, vous réduisez le risque de rencontrer des expériences négatives en raison du périphérique lui-même (ce qui est plus probable, par exemple, avec les microphones et haut-parleurs intégrés). Pour plus d’informations, consultez [les téléphones et périphériques pour Skype pour les entreprises](https://technet.microsoft.com/office/dn947482).

#### <a name="organizational-usage-of-capture-devices-microphones-by-volume"></a>Utilisation des périphériques de capture (microphones) en volume d’organisation

Ce rapport est utilisé pour évaluer l’utilisation du microphone par volume et score de MOS et peut être trouvé dans les modèles d’accompagnement sous Clients et périphériques*.*

> [!IMPORTANT]
> Rapports sur les périphériques vous obligent à exclure les données participants fédérées. Pour exclure les données participants fédérées, vous devez ajouter un filtre de requête pour **Second ID de clients** de votre organisation [d’ID de client](#tenant-id). 

> [!NOTE] 
> Veillez à régler le filtre de l’année du mois pour le mois en cours. Sélectionnez **Modifier**, puis modifiez les **Mois année** pour enregistrer le nouveau mois par défaut.<br><br> Vous remarquerez que lorsque l’affichage rapport de ce que vous voyez le même périphérique signalé plusieurs fois. Il s’agit à la manière dont le périphérique est signalé signalée au CQD. Différences dans le matériel et les paramètres régionaux du système d’exploitation rapport différemment les données de périphérique.

![Capture d’écran de l’état des périphériques (Microphone) dans le tableau de bord qualité appeler.](media/quality-of-experience-review-guide-image29.png)

_La figure 29 - – rapport de périphérique (Microphone)_

##### <a name="remediation"></a>Mise à jour

La première tâche consiste à déterminer la cible MOS que vous souhaitez atteindre. MOS scores compris entre 1 et 5, avec 5 étant la meilleure note. Choisissez une cible raisonnable, en fonction de votre environnement et les résultats de la requête. Dans l’exemple suivant, la cible est un score MOS de 3.6 ou supérieur pour tous les périphériques qui ont plus de 100 flux. Vous obtiendrez ainsi la qualité de votre périphérique cible lorsque :

-   Résultats de la requête de dispositif MOS de retour \> 3.6 pour NumStreams \> 100

En règle générale, vous devez remplacer les périphériques médiocres avec les périphériques certifiés. Certaines considérations lors de l’examen de l’état du périphérique sont les suivantes :

-   Sont les périphériques certifiés ou connus pour être utile dans votre environnement ? Si un périphérique certifié ou bien est retourné dans la requête avec un score de MOS inférieur que votre ligne de base, il est peut-être inconnu des facteurs supplémentaires (par exemple, un réseau est mauvaise ou un pc sous-alimenté) servant au score faible.
    Des recherches supplémentaires seront nécessaires.

-   Vous pouvez identifier les utilisateurs d’un périphérique à [Appeler l’Analytique](#call-analytics-training). Vérifiez pour vous assurer qu’ils ont les derniers pilotes de périphérique et que leur équipement n’est pas connecté à un concentrateur USB.

-   Vérifiez s’il existe une corrélation entre les périphériques défectueux et les marque d’un système particulier et le modèle. Dans ce cas, le périphérique peut être incompatible ou ont besoin de mises à niveau du pilote.

La deuxième tâche consiste à déterminer l’utilisation de périphériques non certifiés. Nous recommandons d’utiliser un périphérique certifié au moins 80 % de tous les flux audio.
Cela est mieux réalisée par l’exportation de l’état des périphériques vers Excel et manuellement du calcul de l’utilisation de périphériques certifiés ou approuvés. Les organisations conservent généralement une liste de tous les périphériques approuvés, filtrage et tri des données doivent être simples.

## <a name="appendix-a-lync-networking-guide"></a>Guide de mise en réseau l’appendice A. Lync

Pour plus d’informations sur les équipes et Skype pour des concepts de réseau d’entreprise et les raisons qui justifient leur importance pour la qualité, le [Guide de mise en réseau de Lync Server 2013](https://blogs.technet.microsoft.com/nexthop/2013/06/03/lync-server-2013-networking-guide-network-planning-monitoring-and-troubleshooting-with-microsoft-lync-server/) est toujours applicable.

## <a name="appendix-b-network-performance-requirements"></a>Exigences de performance de l’appendice B. réseau

La qualité du support en temps réel (audio, vidéo et partage d’application) sur IP est considérablement affectée par la qualité de la connectivité réseau de bout en bout. Pour des équipes ou des Skype pour Business Support de qualité optimale, votre réseau doit respecter les métriques de performances réseau suivant.

_Tableau 11 - exigences de performances réseau_

| Mesure                           | Client vers Microsoft Edge           | Périphérie client vers Microsoft Edge    |
|----------------------------------|------------------------------------|------------------------------------|
| Latence (unidirectionnel)                | \<50 ms                            | \<30 ms                            |
| Latence (RTT ou temps d’aller-retour) | \<100 ms                           | \<60 ms                            |
| Perte de paquets en mode rafale                | \<10 % au cours de n’importe quel intervalle de 200-ms   | \<1 % au cours de n’importe quel intervalle de 200-ms    |
| Perte de paquets                      | \<1 % au cours de l’intervalle de 15-s    | \<0,1 % au cours de l’intervalle de 15-s  |
| Paquet arrivée entre GIGUE      | \<30 ms pendant un intervalle de 15-s | \<15 ms pendant un intervalle de 15-s |
| Réorganisation des paquets                   | \<paquets à la sortie de commande 0,05 %       | \<paquets de 0,01 % à la sortie de commande      |

Pour plus d’informations, voir l’article suivant sur des [média qualité et les performances réseau](https://aka.ms/performancerequirements) pour les équipes et Skype pour l’activité en ligne.

<a name="other-resources"></a>

## <a name="appendix-c-other-resources"></a>Annexe C. Autres ressources

### <a name="building-data-file"></a>Fichier de données de construction

-   [Mise sous tension et l’utilisation de CQD dans Skype pour professionnels en ligne](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-in-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)

<a name="CQD-training"></a>

### <a name="cqd-training"></a>Formation de CQD

-   <https://aka.ms/sof-cqd>

-   Guide de [mise en route de la CQD](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Configuring%20Call%20Quality%20Dashboard%20to%20monitor%20your%20Skype%20for%20Business%20Online%20Environment) et l’atelier.

-   [Les mesures et les Dimensions du CQD guide en ligne](https://support.office.com/article/Dimensions-and-measures-available-in-Call-Quality-Dashboard-in-Skype-for-Business-Online-e97aeeee-9e43-416f-b433-9cdd63d8874b)

### <a name="call-analytics-training"></a>Formation d’Analytique d’appel

-   [Présentation Analytique de l’appel](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)

-   [Configurer l'analyse des appels Skype Entreprise](https://support.office.com/article/Set-up-Skype-for-Business-Call-Analytics-FBF7247A-84AE-46CC-9204-2C45B1C734CD)

-   [En quoi l'analyse des appels et le tableau de bord de qualité des appels sont-ils différents ?](https://support.office.com/article/What-s-the-difference-between-Call-Analytics-and-Call-Quality-Dashboard-4CD5FE35-8463-4996-A252-086CD3CA2D9A)

-   [Utiliser l'analyse des appels pour résoudre les problèmes liés à la qualité médiocre des appels Skype Entreprise](https://support.office.com/article/Use-Call-Analytics-to-troubleshoot-poor-Skype-for-Business-call-quality-66945036-ae87-4c08-a0bb-984e50d6b009)

### <a name="call-analytics-support"></a>Appelez le support Analytique

-   Communauté : [Skype pour le programme d’évaluation entreprise](https://techcommunity.microsoft.com/t5/Skype-for-Business-Preview/bd-p/SkypeforBusinessPreviewProgram)

-   Pour obtenir de l’assistance, connectez-vous à notre portail d’aperçu [www.skypepreview.com](http://www.skypepreview.com), sélectionnez **l’état d’un problème**et utiliser l’option **Créer un nouveau bogue** pour signaler un problème. Veuillez noter que les ingénieurs du support technique sont disponibles pour prendre en charge à partir du lundi au vendredi, de 06 h 00 à 9 h HNE. Demandes en dehors de ces heures de triage seront le jour suivant.

### <a name="devices"></a>Périphériques

-   [Skype pour Business Solutions catalogue périphériques personnels et les PC](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

### <a name="tenant-reporting"></a>Création de rapports de clients

-   [Pack de contenu Adoption Office 365](https://blogs.office.com/2017/05/22/announcing-the-public-preview-of-the-office-365-adoption-content-pack-in-powerbi/)

-   [Création de rapports Skype Entreprise Online](https://support.office.com/article/Skype-for-Business-Online-reporting-4935cddf-fafa-442d-91a3-246af01f8373)

-   [Teams de création de rapports de Microsoft](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/New-usage-reports-for-Microsoft-Teams/ba-p/132614)
