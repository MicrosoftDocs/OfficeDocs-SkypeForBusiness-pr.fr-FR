---
title: Centre de contacts teams
author: microsoftheidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: anblak
localization_priority: Normal
f1.keywords:
- NOCSH
description: Présentation de la solution Centre de contacts intégré en tant que service (CCaaS) de Microsoft teams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0fb65edc260c5a91ee51a32c6c3796e2773ba179
ms.sourcegitcommit: 54e685b07d1c23100951d46913480989f046d534
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/02/2020
ms.locfileid: "48827738"
---
# <a name="contact-center-integrations-for-microsoft-teams"></a>Intégrations du centre de contacts pour Microsoft teams

L’intégration des solutions populaires du centre de contacts avec Microsoft teams est un bon besoin pour les clients qui déploient les fonctionnalités d’appel d’équipes.  Cet article fournit une vue d’ensemble de la façon dont les solutions du centre de contacts peuvent être intégrées à Microsoft Teams, ainsi que des informations supplémentaires sur les solutions de partenariat qui participent au programme de certification du centre de contacts Microsoft Teams.

## <a name="what-is-a-contact-center-integration-for-microsoft-teams"></a>Qu’est-ce qu’une intégration du centre de contacts pour Microsoft teams ?

Les centres de contacts actuels fournissent bien plus d’assistance technique : ils agissent comme l’un des principaux moyens d’interactions et de commentaires non filtrés sur l’environnement d’un client avec une marque. En raison de la variété de canaux qu’il est préférable d’impliquer sur le téléphone, le courrier électronique, le texte, la mise en réseau et le volume de points de contact étendus associés aux processus d’achat de la journée de présentation, de nombreuses organisations ont réalisé deux réalités supplémentaires :

1. Tous les membres de l’organisation peuvent se servir de l’implication directe d’un client, et par conséquent doivent être équipés des outils appropriés.

2. Ce cadre étendu d’interactions client nécessite des outils qui permettent d’améliorer la cohérence, l’amélioration constante et la mise à l’échelle.

Microsoft teams prend en charge les flux de tâches d’interactions client en agissant en tant que concentrateur pour les connexions clientes internes et externes dans ses modes de communication, notamment les discussions, les réunions vidéo et les appels. Pour certaines sociétés, les fonctionnalités de [voix Cloud](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page)de Microsoft Teams, y compris le [standard automatique](https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants) et les [files d’attente d’appels](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue), fournissent les fonctionnalités et la configuration qui répondent à leurs besoins.

Pour les personnes qui ont besoin de solutions intégrées avec des outils et des flux de travail pour favoriser le voyage du client, Microsoft teams s’intègre également à certaines des fournisseurs de solutions de service (CCaaS) de l’industrie.

## <a name="connected-contact-center-for-microsoft-teams-certification-program"></a>Centre de contacts connecté pour le programme de certification Microsoft teams

Les API permettent aux partenaires de développer et d’intégrer les solutions CCaaS pour Teams. En outre, nous avons développé le centre de coordonnées connecté pour le programme de certification de Microsoft teams pour fournir aux clients l’assurance que les solutions de chaque partenaire participant ont été testées et vérifiées pour garantir la qualité, la compatibilité et la fiabilité de leurs solutions Microsoft.

Les partenaires suivants travaillent dans le processus de certification de leur solution pour Microsoft teams et sont prêts à engager les clients :

|  Partenaire                                                                                                                               |  Site Web de solution                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| ---------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Anywhere365 | https://anywhere365.io/direct-routing-contact-center-for-microsoft-teams/                                      |
| Competella | https://www.competella.com/microsoft-teams-skype-for-business                                  |
| ComputerTalk | https://www.computer-talk.com/product/enterprise-contact-center/ice-contact-center-for-teams         |
| ContactCenter4All | www.contactcenter4all.com |
| Enghouse interactif | http://www.enghouseteams.com/                                                       |
| Five9 | https://www.five9.com/products/application-integration/uc-integration                                                   |
| Genes | https://www.genesys.com/microsoft                                                                                   |
| Technologies Landis | https://landistechnologies.com/microsoft-teams-contact-center/                                          |
| Luware | https://luware.com/en/solutions/                                                                                       |
| NICE contact | https://www.niceincontact.com/microsoft-teams                                                            |
| Novomind | https://www.novomind.com/en/customer-service-software-call-center/microsoft-teams/                             |
| Tendfor | https://www.tendfor.com/en/                                                                                     |

Cette liste sera mise à jour sous la forme d’autres partenaires et répondez aux critères de certification.

## <a name="how-do-contact-center-solutions-work-in-microsoft-teams"></a>Comment fonctionnent les solutions du centre de contacts dans Microsoft teams ?

Microsoft teams offre une gamme de fonctionnalités permettant de soutenir le développement de solutions vocales tierces, notamment :

1. [Connectivité du routage direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

2. [API de communication Cloud de Microsoft Graph](https://docs.microsoft.com/graph/cloud-communications-get-started)

3. Plateforme et extensibilité teams

4. SDK teams

Ensemble, ces fonctionnalités permettent trois modèles d’intégration :

  - **Connexion** (via le routage direct)

  - **Se connecter et prolonger** (routage direct, API de graphique et plateforme d’applications Teams)

  - **Extension et alimentation (mise** en application de SDK teams dans 3P pour les interactions d’équipes natives)

### <a name="connect"></a>Connecté

Ce modèle connecte les partenaires CCaaS avec l’infrastructure du système téléphonique de Microsoft Teams, ce qui permet d’améliorer le routage, la configuration et l’analyse du système. Dans ce modèle, la solution de partenariat du centre de contacts peut également fournir des services de téléphonie pour les numéros et utilisateurs sélectionnés.

Les agents qui utilisent des solutions bâties sur le modèle de connexion peuvent collecter des informations & Insights et, si nécessaire, transférer directement des appels à des experts, en profitant de la présence du SME dans Teams, afin de garantir leur disponibilité.

Les organisations peuvent s’assurer que les appels sont dirigés vers l’agent optimal en configurant des assistants virtuels automatisés et des files d’attente de routage basées sur les compétences.

**Principales fonctionnalités :**

Comme Voici une liste complète des fonctionnalités de fonctionnalité pour ce modèle d’intégration, les zones principales sont les suivantes :

  - Office 365 Authn pour les agents pour permettre aux agents de se connecter à leur client Microsoft à partir de leur client CCaaS intégré 

  - Indication de présence des utilisateurs de teams 

  - Flux d’appels via le routage direct (comme indiqué dans les plans de test) 

  - Prenez en charge les transferts et les appels de groupe avec les utilisateurs teams 

  - API du graphique teams et API de communication Cloud pour l’intégration à teams 

  - Capable de prendre en charge le trunking SIP multipoint pour la prise en charge de plusieurs clients sur les SBC du partenaire.  

  - Partenaires permettant d’implémenter [ <span class="underline">Microsoft Certified session Controller (SBC)</span>](https://docs.microsoft.com/MicrosoftTeams/direct-routing-border-controllers) 

### <a name="connect-and-extend"></a>Se connecter et prolonger

Ce modèle étend le personnel du centre de contacts et les expériences des agents en intégrant le client teams à l’aide de la [plate-forme du client teams](https://docs.microsoft.com/microsoftteams/platform/overview), des [API teams Graph](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0) et [de l’API de communications Cloud dans Microsoft Graph](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) et utilise le système téléphonique teams pour tous les appels du centre de contacts et des expériences de contrôle d’appel. Dans ce modèle, le partenaire du centre de contacts joue le rôle d’opérateur de téléphonie parallèlement à Microsoft 365.

En tirant parti des solutions de connexion et d’extension, les agents peuvent tirer parti de notes dynamiques et contextuelles mettant en corrélation les données de plusieurs systèmes avant de commencer un engagement, puis éviter le changement de contexte coûteux en travaillant en mode natif dans teams pour la collaboration interne et les communications externes.

Les organisations peuvent concevoir des flux de travail et des configurations de routage avancées vers leurs utilisateurs et mesurer la qualité de leurs systèmes et interactions.

**Principales fonctionnalités :**

Comme Voici une liste complète des fonctionnalités de fonctionnalité pour ce modèle d’intégration, il met en évidence les principales zones de foyer :

  - API du graphique teams et API de communication Cloud pour l’intégration à teams 

  - Expériences d’applications basées sur teams 

  - Teams comme point de terminaison d’appelant principal pour les agents 

  - Appel client teams pour tous les contrôles d’appel

  - L’application de l’interface utilisateur doit être en mesure de fonctionner sur les sites Web des équipes et sur les appareils mobiles.

  - Analyse, gestion du flux de travail, expériences basées sur les rôles pour les agents au sein de l’application CCaaS dans teams

  - Expériences de conversation et de collaboration intégrées aux clients teams 

  - Préservation des performances et de la qualité des expériences client d’équipes dans toutes les applications  

### <a name="extend-and-power"></a>Extension et alimentation

Ce modèle permet aux partenaires de créer des applications vocales Azure natives tirant parti de l’infrastructure des équipes appelante et de la plate-forme du client pour la fourniture de solutions modernes et intelligentes pour une connexion de client et d’agent collaborative. L’objectif du développement et de la puissance est d’Stoker la créativité du développeur et de dynamiser la productivité du client.

En construisant directement sur Azure, les partenaires peuvent rapidement déployer et approvisionner leur solution dans toutes les régions et zones géographiques d’équipe, Benefitting de notre réseau partagé de communications globales tout en tirant parti du stockage, des calculs, des analyses & services cognitifs d’Azure.

Grâce au modèle prolonger et intégration de l’alimentation, les partenaires peuvent fournir des agents du centre de contacts avec des expériences de communication Omni-canal tout en incorporant des informations sur l’utilisation de l' [API de communications Cloud dans Microsoft Graph](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0).

**Principales fonctionnalités :**

Comme Voici une liste complète des fonctionnalités de fonctionnalités pour ce modèle d’intégration, celles-ci sont des zones en surbrillance en plus de celles fournies par le modèle de connexion et d’extension.

  - L’agent formel a activé en natif la communication Omni-canal par le biais du SDK teams 

  - Exploitez les services de collaboration en équipes pour la collaboration et les interactions client  

  - Attribution rapide de services Cloud, déploiement en tout lieu 

  - Contrôle de conversation directe et interaction avec les utilisateurs lors des conversations d’équipes 

### <a name="comparing-connected-contact-center-integration-models"></a>Comparaison des modèles d’intégration de centre de contacts connectés

Consultez le tableau ci-dessous pour obtenir une vue d’ensemble des modèles d’intégration pris en charge par Microsoft Teams.

<table>
<thead>
<tr class="header">
<th></th>
<th>Applications vocales teams</th>
<th>Connecté</th>
<th>Étendre</th>
<th>Pouvoirs</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Modèle de service Cloud</td>
<td>Bleu</td>
<td>Partenaire</td>
<td><p>Partenaire +</p>
<p>Bleu</p></td>
<td>Bleu</td>
</tr>
<tr class="even">
<td>Qui fonctionne avec la solution ?</td>
<td>Microsoft</td>
<td>Partenaire</td>
<td>Partenaire</td>
<td>Partenaire</td>
</tr>
<tr class="odd">
<td>Connexion M365</td>
<td>Oui</td>
<td>Oui</td>
<td>Oui</td>
<td>Oui</td>
</tr>
<tr class="even">
<td>Utilisateurs avec teams appelant</td>
<td>Informel, PME</td>
<td>Informel, PME</td>
<td>Informel, SME, formel</td>
<td>Informel, SME, formel</td>
</tr>
<tr class="odd">
<td>Expertise IW et SME</td>
<td>Teams</td>
<td>Teams</td>
<td><p>Teams +</p>
<p>variable</p></td>
<td><p>Teams +</p>
<p>variable</p></td>
</tr>
<tr class="even">
<td>Service Connectivity</td>
<td>Plateforme<br />
(Plans d’appel + DR)</td>
<td>Routage direct</td>
<td>Plateforme<br />
(Plans d’appel + DR)</td>
<td>Plateforme<br />
(Plans d’appel + DR)</td>
</tr>
</tbody>
</table>

## <a name="next-steps"></a>Étapes suivantes

Si vous êtes un fournisseur qui cherche à rejoindre le programme de certification, envoyez-le par e-mail <Teamscategorypartner@microsoft.com> .
