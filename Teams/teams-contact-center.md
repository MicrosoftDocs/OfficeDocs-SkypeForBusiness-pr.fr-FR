---
title: Centre de contacts Teams
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
description: Vue d’ensemble du centre de contacts intégré en tant que solution de service (CCaaS) pour Microsoft Teams
appliesto:
- Microsoft Teams
ms.openlocfilehash: d34a1790a082e1defab399828cceb5c0082dc70d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909488"
---
# <a name="contact-center-integrations-for-microsoft-teams"></a>Intégrations du Centre de contacts pour Microsoft Teams

L’intégration des solutions de centre de contacts populaires à Microsoft Teams est un besoin courant de clients qui déploient des fonctionnalités d’appel d’équipes.  Cet article fournit une vue d’ensemble de la manière dont les solutions du centre de contacts peuvent être intégrées avec Microsoft Teams et des informations supplémentaires sur les solutions de partenaire participant au Programme de certification du Centre de contacts connecté à Microsoft Teams.

## <a name="what-is-a-contact-center-integration-for-microsoft-teams"></a>Qu’est-ce qu’une intégration du Centre de contacts pour Microsoft Teams ?

Aujourd’hui, les centres de contacts offrent bien plus que du support: ils font partie des principaux utilitaires d’interaction et de commentaires non filtrés sur l’expérience d’un client avec une marque. En raison de l’éventail des canaux que les clients aujourd’hui préfèrent s’impliquer :téléphone, courrier électronique, texte, réseaux sociaux, et le volume développé de points tactiles associés aux processus d’achat actuels. De nombreuses organisations ont fait l’expérience de deux réalités supplémentaires :

1. Chaque membre de l’organisation peut participer directement à l’implication d’un client et doit donc être équipé des outils appropriés.

2. Cette étendue étendue des interactions avec le client nécessite des outils qui contribuent à la cohérence, à l’amélioration constante et à l’échelle.

Microsoft Teams prend en charge les flux de travail d’interaction client en agissant comme concentrateur pour la connexion des clients internes et externes entre ses modes de communication, notamment les discussions instantanées, les réunions vidéo et les appels. Pour certaines entreprises, les fonctionnalités vocales [cloud](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page)de Microsoft Teams, notamment le [attendant](https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants) automatique et les files d’attente d’appels, fournissent les [fonctionnalités](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue)et la configuration nécessaires.

Si d’autres personnes souhaitent intégrer des solutions à des outils et flux de travail d’entreprise pour mener à bien le parcours client, Microsoft Teams s’intègre également avec certains fournisseurs de solutions CCaaS (Centre de contacts en tant que service) leaders du secteur.

## <a name="connected-contact-center-for-microsoft-teams-certification-program"></a>Centre de contacts connectés pour le programme de certification de Microsoft Teams

Les API permettent aux partenaires de développer et d’intégrer des solutions CCaaS pour Teams. Nous avons également développé le Centre de contacts connectés pour le programme de certification de Microsoft Teams afin de fournir aux clients la assurance que la solution de chaque partenaire participant a été testée et vérifiée afin de fournir la qualité, la compatibilité et la fiabilité qu’ils attendent des solutions Microsoft.

Les partenaires suivants sont en train de certifier leur solution pour Microsoft Teams et sont prêts à impliquer les clients :

|  Partenaire                                                                                                                               |  Site web de la solution                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| ---------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `8x8` | https://www.8x8.com/products/integrations/8x8-voice-for-microsoft-teams?locale=us |
| `Anywhere365` | https://anywhere365.io/direct-routing-contact-center-for-microsoft-teams/                                      |
| `Competella` | https://www.competella.com/microsoft-teams-skype-for-business                                  |
| `ComputerTalk` | https://www.computer-talk.com/product/enterprise-contact-center/ice-contact-center-for-teams         |
| `ContactCenter4All` | www.contactcenter4all.com |
| `Content Guru` | https://www.contentguru.com/microsoft-teams-integration/    |
| `Enghouse Interactive` | http://www.enghouseteams.com/                                                       |
| `Five9` | https://www.five9.com/products/application-integration/uc-integration                                                   |
| `Genesys` | https://www.genesys.com/microsoft                                                                                   |
| « Geomant » | https://www.geomant.com/buzzeasy-contact-centre-for-microsoft-teams                                          |
| `Landis Technologies` | https://landistechnologies.com/microsoft-teams-contact-center/                                          |
| `Luware` | https://luware.com/en/solutions/                                                                                       |
| `NICE inContact` | https://www.niceincontact.com/microsoft-teams                                                            |
| `novomind` | https://www.novomind.com/en/customer-service-software-call-center/microsoft-teams/                             |
| `Tendfor` | https://www.tendfor.com/en/                                                                                     |

Cette liste est mise à jour à mesure que de nouveaux partenaires rejoignent et répondent aux critères de certification.

## <a name="how-do-contact-center-solutions-work-in-microsoft-teams"></a>Comment fonctionnent les solutions du Centre de contacts dans Microsoft Teams ?

Microsoft Teams offre une gamme de fonctionnalités qui permet de prendre en charge le développement de solutions vocales tierces, notamment :

1. [Connectivité de routage direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

2. [API de communication cloud Microsoft Graph](https://docs.microsoft.com/graph/cloud-communications-get-started)

3. Plateforme et extensibilité de Teams

4. SDK Teams

Ensemble, ces fonctionnalités permettent trois modèles d’intégration :

  - **Connexion** (via un routage direct)

  - **Connexion et extension** (plateforme des applications Routage direct, API Graph et Teams)

  - **Extension et puissance** (incorporation de SDK Teams dans des applications 3p pour les interactions Teams natives)

### <a name="connect"></a>Connecter

Ce modèle connecte les partenaires CCaaS à l’infrastructure du système téléphonique de Microsoft Teams, ce qui permet d’améliorer le routage, la configuration et les informations système. Dans ce modèle, la solution partenaire du Centre de contacts peut également fournir des services téléphoniques pour certains numéros et utilisateurs.

Les agents utilisant des solutions intégrées au modèle & Connect peuvent recueillir des informations et obtenir des informations et, si nécessaire, transférer des appels à des experts sur ce sujet directement, en utilisant la présence du SME dans Teams pour garantir leur disponibilité.

Les organisations peuvent router les appels vers l’agent optimal en mettant en place des assistants virtuels automatisés et des files d’attente de routage basées sur les compétences.

**Principales caractéristiques de la fonctionnalité :**

Bien que les points suivants ne sont pas une liste exhaustive des fonctionnalités de ce modèle d’intégration, les domaines clés sont les suivants :

  - AuthN Office 365 pour les agents qui autorisent les agents à se connecter à leur client Microsoft à partir de leur client CCaaS intégré 

  - Indication de présence des utilisateurs de Teams 

  - Flux d’appels via un routage direct (comme indiqué dans les plans de test) 

  - Transferts de support et appels de groupe avec les utilisateurs de Teams 

  - API Teams Graph et API de communication cloud pour l’intégration avec Teams 

  - Possibilité de prendre en charge le branchement SIP multi-client pour prendre en charge plusieurs clients sur le SBC du partenaire.  

  - Partenaires pour implémenter le contrôleur de bordure de session certifié [ <span class="underline">Microsoft (SBC)</span>](https://docs.microsoft.com/MicrosoftTeams/direct-routing-border-controllers) 

### <a name="connect-and-extend"></a>Se connecter et prolonger

Ce modèle étend les expériences du personnel et de l’agent du centre de contacts en l’intégrant au client Teams à l’aide de la plateforme [du client Teams,](https://docs.microsoft.com/microsoftteams/platform/overview)des [API Teams Graph](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0) et de l’API de communications cloud dans Microsoft [Graph](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) et utilise le système téléphonique de Teams pour tous les appels du centre de contacts et les expériences de contrôle d’appel. Dans ce modèle, le partenaire du Centre de contacts agit en tant qu’opérateur téléphonique en parallèle de Microsoft 365.

L’utilisation de solutions de connexion et étendues permet aux agents de tirer parti de notes dynamiques et contextuelles qui correlent les données de plusieurs systèmes avant de commencer un engagement, et évitent ainsi un changement de contexte coûteux en travaillant en mode natif dans Teams pour la collaboration interne et les communications externes.

Les organisations peuvent concevoir des flux de travail et des configurations de routage avancées jusqu’à la personne et mesurer la qualité de leur système et de leurs interactions.

**Principales caractéristiques de la fonctionnalité :**

Bien que la liste suivante ne soit pas exhaustive des fonctionnalités de ce modèle d’intégration, elle met en évidence les principaux domaines clés :

  - API Teams Graph et API de communication cloud pour l’intégration avec Teams 

  - Application Teams pour les expériences de l’agent 

  - Teams comme point de terminaison d’appel principal pour les agents 

  - Appel du client Teams pour tous les contrôles d’appel

  - L’application expérience de l’agent doit également pouvoir fonctionner sur teams web et sur un client mobile

  - Analyse, gestion des flux de travail, expériences basées sur les rôles pour les agents au sein de l’application CCaaS dans Teams

  - Les expériences de conversation et de collaboration intégrées aux clients Teams 

  - Préserver les performances et la qualité des expériences clientes de Teams dans toutes les applications  

### <a name="extend-and-power"></a>Étendre et alimenter

Ce modèle permet aux partenaires de créer des applications vocales azure natives à l’aide de l’infrastructure d’appels Teams et de la plateforme cliente pour offrir des solutions modernes et intelligentes pour une connexion client et agent collaborative. L’objectif de Développer et de Power est de stimuler la créativité des développeurs et de stimuler la productivité des clients.

En construisant directement sur Azure, les partenaires peuvent rapidement déployer et déployer leur solution dans toutes les régions et régions géographiques de Teams, en profitant de notre réseau de communications partagé et global, tout en profitant des services cognitifs &, de calcul, d’analyse et de stockage Azure.

Avec le modèle d’intégration extend et Power, les partenaires peuvent fournir aux agents des centres de contacts des expériences de communication sur l’ensemble des canaux, tout en intégrant l’intelligence artificielle pour personnaliser la façon dont les participants, ou d’autres services, participent à un appel appliquant l’API de communications cloud dans [Microsoft Graph.](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0)

**Principales caractéristiques de la fonctionnalité :**

Bien que la liste suivante ne soit pas exhaustive des fonctionnalités de ce modèle d’intégration, ces aspects mis en évidence s’ajoutent à ceux fournis par le modèle Se connecter et étendre.

  - Expériences formelles de l’agent activées en natif pour la communication sur tout canal via le SDK Teams 

  - Utiliser les services de collaboration dans Teams pour la collaboration avec les agents et les interactions avec les clients  

  - Approvisionnement rapide des services cloud, déploiement en tout lieu 

  - Direct conversation control and interaction with users during Teams conversations 

### <a name="comparing-connected-contact-center-integration-models"></a>Comparaison des modèles d’intégration des centres de contacts connectés

Le tableau ci-dessous présente une vue d’ensemble des modèles d’intégration que Microsoft Teams prend en charge.

<table>
<thead>
<tr class="header">
<th></th>
<th>Applications vocales Teams</th>
<th>Connecter</th>
<th>Étendre</th>
<th>Alimentation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Modèle de service cloud</td>
<td>Azure</td>
<td>Partenaire</td>
<td><p>Partenaire +</p>
<p>Azure</p></td>
<td>Azure</td>
</tr>
<tr class="even">
<td>Qui gère la solution ?</td>
<td>Microsoft</td>
<td>Partenaire</td>
<td>Partenaire</td>
<td>Partenaire</td>
</tr>
<tr class="odd">
<td>M365 Sign-in</td>
<td>Oui</td>
<td>Oui</td>
<td>Oui</td>
<td>Oui</td>
</tr>
<tr class="even">
<td>Vous appelez des utilisateurs de Teams ?</td>
<td>Informel, SME</td>
<td>Informel, SME</td>
<td>Informel, SME, Formel</td>
<td>Informel, SME, Formel</td>
</tr>
<tr class="odd">
<td>Expérience IW/SME</td>
<td>Teams</td>
<td>Teams</td>
<td><p>Teams +</p>
<p>extensions</p></td>
<td><p>Teams +</p>
<p>extensions</p></td>
</tr>
<tr class="even">
<td>Connectivité des services</td>
<td>Plateforme<br />
(Forfaits d’appels +DR)</td>
<td>Routage direct</td>
<td>Plateforme<br />
(Forfaits d’appels + DR)</td>
<td>Plateforme<br />
(Forfaits d’appels + DR)</td>
</tr>
</tbody>
</table>

## <a name="next-steps"></a>Étapes suivantes

Si vous êtes un vendeur désireux de participer au programme de certification, envoyez un <Teamscategorypartner@microsoft.com> e-mail.
