---
title: Rapport d'utilisation du réseau téléphonique commuté
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 74eda791-c41f-4fd9-ae0b-913342e7ab04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: La nouvelle zone rapports du centre d’administration Skype entreprise vous permet d’afficher les appels et les activités de conférence audio au sein de votre organisation. Elle vous permet d’explorer des rapports pour vous offrir une vue plus granulaire des activités de chaque utilisateur. Le rapport sur les détails d'utilisation PSTN de Skype Entreprise vous permet par exemple d'afficher le nombre de minutes passées pour des appels entrants ou sortants ainsi que les coûts de ces appels. Vous pouvez afficher les détails d’utilisation RTC de l’audioconférence, y compris le coût de l’appel, afin de comprendre l’utilisation et les détails de facturation pour déterminer l’utilisation au sein de votre organisation.
ms.openlocfilehash: 4161f0f9f0b6e011b67f94afc14b5ac793fc1009
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776269"
---
# <a name="pstn-usage-report"></a>Rapport d'utilisation du réseau téléphonique commuté

La nouvelle zone **rapports** du centre d’administration Skype entreprise vous permet d’afficher les appels et les activités de conférence audio au sein de votre organisation. Elle vous permet d’explorer des rapports pour vous offrir une vue plus granulaire des activités de chaque utilisateur. Le rapport sur les **détails d'utilisation PSTN de Skype Entreprise** vous permet par exemple d'afficher le nombre de minutes passées pour des appels entrants ou sortants ainsi que les coûts de ces appels. Vous pouvez afficher les détails d’utilisation RTC de l’audioconférence, y compris le coût de l’appel, afin de comprendre l’utilisation et les détails de facturation pour déterminer l’utilisation au sein de votre organisation.
  
Consultez la [vue d’ensemble des rapports](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) pour plus d’informations sur les rapports disponibles.
  
Ce rapport, ainsi que les autres rapports Skype entreprise, vous fournissent des informations sur les activités, y compris l’utilisation des appels au sein de votre organisation. Ces informations sont très utiles lorsque vous effectuez des recherches, planifiez et organisez d’autres décisions d’entreprise pour votre organisation et que vous configurez des [crédits de communication](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Vous pouvez afficher tous les rapports Skype entreprise lorsque vous vous connectez en tant qu’administrateur au centre d’administration Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Comment obtenir les rapports sur les détails d'utilisation PSTN de Skype Entreprise

![Icône affichant le logo Skype Entreprise](../images/sfb-logo-30x30.png) **Utiliser le Centre d’administration Skype Entreprise**

- Accédez au centre d' **administration >** > Centre d’administration Skype entreprise-**rapports** >  > **Centre d’administration Skype entreprise**-**Détails d’utilisation PSTN**.
    
    > [!NOTE]
    > En fonction de l’abonnement Microsoft 365 ou Office 365, vous ne verrez peut-être pas tous les produits et les rapports présentés dans cet article.
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>Interpréter le rapport d'utilisation PSTN de Skype Entreprise

Vous pouvez vous connaître l'utilisation PSTN Skype Entreprise d'un utilisateur en consultant chacune des colonnes qui sont affichées.
  
Voici une illustration du rapport.
  
![Rapport d'utilisation de la conférence RTC Skype Entreprise](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)

***
![Numéro 1](../images/sfbcallout1.png)<br/>Le tableau présente une répartition par utilisateur de toutes les utilisations PSTN. Cette opération montre tous les utilisateurs pour lesquels Skype entreprise est associé et leur utilisation PSTN. Vous pouvez ajouter ou supprimer des colonnes dans ce tableau.
*    **ID d’appel** est l’ID d’appel d’un appel. Il s’agit d’un identificateur pour l’appel qui est utilisé lors de l’appel du service de support technique Microsoft.
*    **ID de l'utilisateur** est le nom de connexion de l'utilisateur.
*    **Numéro de téléphone** correspond au numéro de téléphone skype entreprise qui a reçu l’appel d’appels entrants ou du numéro numéroté pour les appels sortants.
*    **Emplacement** de l’utilisateur est le pays ou la région où se trouve l’utilisateur.
*    **ID** de l’appelant correspond au numéro de téléphone (ID d’appelant) de l’appelant pour les appels entrants, le numéro à partir duquel provient l’appel ou le numéro Skype entreprise à partir duquel il a été émis pour les appels sortants.
*    **Type d’appel** indique si l’appel était un appel RTC entrant ou sortant ainsi que le type d’appel passé par un utilisateur ou une conférence audio. Les types d’appels que vous pouvez voir : 

     **Types d’appels de plan d’appels** 
     *    **user_in** (l’utilisateur a reçu un appel RTC entrant) 
     *    **user_out** (l’utilisateur a passé un appel RTC sortant) 
     *    **user_out_conf** (l’utilisateur a ajouté 2 personnes ou plus de participants PSTN à l’appel, par exemple une conférence téléphonique à trois directions) 
     *    **user_out_transfer** (l’utilisateur a transféré l’appel vers un numéro PSTN) 
     *    **user_out_forwarding** (l’utilisateur a transféré l’appel vers un numéro PSTN)

     **Types d’appels de conférence audio**
     *    **conf_in** (appel entrant vers le pont de conférence audio). Pour les enregistrements de ce type d’appel, l’utilisateur spécifié dans la colonne **ID d’utilisateur** correspond à l’organisateur de la réunion.
     *    **conf_out** (un appel sortant à partir du pont de conférence audio, généralement pour ajouter un numéro PSTN à la Conférence). Pour les enregistrements de ce type d’appel, l’utilisateur spécifié dans la colonne **ID d’utilisateur** correspond à l’organisateur de la réunion.

     **Applications de communication unifiée (UCAP)** 
     *    **ucap_in** (un appel RTC entrant vers l’application de communications unifiées, tel que le standard automatique ou la file d’attente d’appels) 
     *    **ucap_out** (appel RTC sortant depuis l’application de communications unifiées, comme standard automatique ou file d’attente d’appels)
     *    **Remarque :** Les appels transférés vers un utilisateur à partir de l’application de communications unifiées, tels qu’un standard automatique ou une file d’attente d’appels, n’apparaissent pas dans le rapport d’utilisation RTC, car ces appels sont des appels audio d’égal à égal (P2P). Vous pouvez accéder aux appels P2P dans le centre d’administration de Skype entreprise, sous « outils > analyse des appels Skype entreprise » et rechercher en fonction du nom d’utilisateur ou de l’adresse SIP en corrélation avec l’appel par date/heure et/ou CLID d’origine (ID de ligne d’appel). 
*     
     **National/international** vous indique si l’appel qui a été placé était considéré comme national (dans un pays ou une région) ou international (à l’extérieur d’un pays ou d’une région) en fonction de l’emplacement de l’utilisateur. 
*    **Composé composé** est le nom de la destination du pays/de la région qui est numérotée comme France, Allemagne ou les États-Unis. 
*    **Type de numéro** est le type de numéro de téléphone qui provient du numéro de téléphone d’un utilisateur, d’un service ou d’un numéro sans frais.  
*    **Heure de début (UTC)** est l'heure à laquelle l'appel a commencé. 
*    **Durée** indique le temps de connexion de l'appel.  
*    **ConfID** est l’ID de conférence de la conférence audio. 
*    **Débit** est le montant d’argent ou le coût de l’appel débité sur votre compte. 
*    **Devise** correspond au type de devise utilisé pour calculer le coût de l’appel. 
*    **Capability** est la licence utilisée pour l’appel. Les types de licence qui peuvent s’afficher sont les suivants : 
     *    **MCOPSTNPP** -crédits de communication <br/> **MCOPSTN1** -forfait d’appels nationaux (3000 min US/1200 min Europe) 
     *    **MCOPSTN2** -forfait d’appels internationaux 
     *    **MCOPSTN5** -forfait d’appels nationaux (forfait d’appels min 120) 
     *    **MCOPSTN6** -forfait d’appels nationaux (forfait d’appels min 240) Remarque : disponibilité limitée
     *    **MCOMEETADD** -audioconférence
     *    **MCOMEETACPEA** -audioconférence à la minute
     
> [!NOTE]
> Pour inclure uniquement les appels payants à la minute qui ne sont pas inclus dans votre abonnement d’appel ou de conférence, filtrez le rapport avec la fonctionnalité « MCOPSTNPP ». Cette opération permet de fournir un élément de tous les appels à la minute.  Pour les conférences audio à la minute, filtrez en fonction de « MCOMEETACPEA » au lieu de « MCOPSTNPP ».  

> [!NOTE]
> Vous pouvez également voir « aucune donnée » dans certains champs. « Aucune donnée » signifie que le champ n’est pas applicable au type d’appel ou à la fonctionnalité. 

> [!NOTE]
> Si vous avez un plan d’appels Telstra, vous ne verrez pas les enregistrements des détails des appels dans le rapport d’utilisation PSTN. Veuillez contacter Telstra pour obtenir les exigences de votre rapport. 
***
![Numéro 2](../images/sfbcallout2.png)<br/>Cliquez pour déplacer une colonne vers **Pour regrouper les informations autour d'une colonne en particulier, faites glisser et déplacez l'en-tête de la colonne ici** si vous souhaitez visualiser toutes les données regroupées dans une ou plusieurs colonnes.
 ***

## <a name="exporting-pstn-usage-report"></a>Exportation du rapport d’utilisation RTC

Cliquer ou appuyer sur le bouton **Exporter vers Excel** vous permet de télécharger le rapport d’utilisation PSTN. Vous pouvez exporter des données vers un an au maximum à partir de la date actuelle, sauf si la législation spécifique du pays interdit la conservation des données pour 12 mois.

Cela exportera les données de tous les utilisateurs et vous permettra de trier et de filtrer plus simplement pour une analyse ultérieure.

Le processus d’exportation peut durer de quelques secondes à quelques minutes, en fonction de la quantité de données. Lorsque le serveur effectue l’exportation, vous recevez un fichier zip intitulé «**appels. Export. [ ] `identifier`. zip**", avec l’identificateur qui est un ID unique pour l’exportation, qui peut être utilisé pour la résolution des problèmes.

Si vous avez les deux plans d’appel et le routage direct, le fichier exporté risque de contenir des données pour les deux produits. Un fichier de rapport d’utilisation RTC porte le nom de fichier «**RTC. Calls ». ] `UTC date`. csv**. Outre les fichiers RTC et de routage directe, l’archive contient le fichier «**Parameters. JSON**», avec la plage de temps d’exportation sélectionnée et les capacités (le cas échéant).

Le fichier exporté est un fichier de valeurs séparées par des virgules (CSV), conforme à la norme [RFC 4180](https://tools.ietf.org/html/rfc4180) . Le fichier peut être ouvert dans Excel ou tout autre éditeur compatible standard sans qu’il soit nécessaire de transformations.

La première ligne du fichier CSV contient les noms des colonnes.

### <a name="fields-in-the-export"></a>Champs lors de l’exportation

Le fichier exporté contient d’autres champs qui ne sont pas disponibles dans le rapport en ligne. Celles-ci peuvent être utilisées pour résoudre les problèmes et les flux de travail automatisés.

| #  | Nom | [Type de données (SQL Server)](https://docs.microsoft.com/sql/t-sql/data-types/data-types-transact-sql) | Description |
| :-: | :-: | :-: |:------------------- |
| 0,4 | UsageId | `uniqueidentifier` | Identificateur d’appel unique |
| 1 | ID d’appel | `nvarchar(64)` | Identifiant de l’appel. Il n’est pas garanti qu’il soit unique. |
| deuxième | ID de conférence | `nvarchar(64)` | ID de la conférence audio |
| 3 | Emplacement de l’utilisateur | `nvarchar(2)` | Code pays de l’utilisateur, [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
| 4 | ObjectId d’argument AAD | `uniqueidentifier` | Appel de l’IDENTIFIant de l’utilisateur dans Azure Active Directory.<br/> Ce type d’informations et d’autres informations sur les utilisateurs seront NULL/vides pour les types d’appels de bot (ucap_in ucap_out) |
| 5 | UPN | `nvarchar(128)` | UserPrincipalName (nom de connexion) dans Azure Active Directory.<br/>Il s’agit généralement de l’adresse SIP de l’utilisateur et peut être identique à l’adresse de messagerie de l’utilisateur. |
| 6 | Nom complet de l’utilisateur | `nvarchar(128)` | Nom d’affichage de l’utilisateur |
| 7 | ID de l’appelant | `nvarchar(128)` | Numéro ayant reçu l’appel pour les appels entrants ou le numéro numéroté pour les appels sortants. Format [E. 164](https://en.wikipedia.org/wiki/E.164) |
| version8 | Type d'appel | `nvarchar(32)` | S’il s’agit d’un appel entrant ou sortant de type RTC et du type d’appel passé par un utilisateur ou une conférence audio. |
| 09 | Type de numéro | `nvarchar(16)` | Type de numéro de téléphone de l’utilisateur, tel qu’un service de numéro gratuit |
| 0,10 | National/international | `nvarchar(16)` | La présence de l’appel national (dans un pays ou une région) ou international (à l’extérieur d’un pays ou d’une région) en fonction de l’emplacement de l’utilisateur |
| 27,9 | Destination numérotée | `nvarchar(64)` | Pays ou région composé |
| midi | Numéro de destination | `nvarchar(32)` | Numéro composé au format [E. 164](https://en.wikipedia.org/wiki/E.164) |
| n°13 | Heure de début | `datetimeoffset` | Heure de début (UTC, [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)) |
| 14 | Heure de fin | `datetimeoffset` | Heure de fin de l’appel (UTC, [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)) |
| 0,15 | Secondes de la durée | `int` | Durée de connexion de l’appel |
| Seiz | Frais de connexion | `numeric(16, 2)` | Prix des frais de connexion |
| Play | Frais | `numeric(16, 2)` | Montant de l’argent ou frais de l’appel facturé sur votre compte. |
| 19 | Devise | `nvarchar(3)` | Type de devise utilisé pour le calcul du coût de l’appel ([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)) |
| 19,6 | Fonctionnalité | `nvarchar(32)` | La licence utilisée pour l’appel |

    
## <a name="want-to-see-other-skype-for-business-reports"></a>Autres rapports d'activité Skype Entreprise

- [Rapport d’activité Skype entreprise](activity-report.md) Vous pouvez visualiser le nombre d’organisations, de participations et de sessions d’égal à égal de conférences par utilisateur.
    
- [Rapport sur l’utilisation des appareils Skype entreprise](device-usage-report.md) Vous pouvez voir les appareils tels que les systèmes d’exploitation Windows et les appareils mobiles sur lesquels l’application Skype entreprise est installée et qui s’en servent pour la messagerie instantanée et les réunions.
    
- [Rapport d’activité d’organisateur de conférences Skype entreprise](conference-organizer-activity-report.md) Vous pouvez visualiser le nombre de conférences de vos utilisateurs à l’aide de la messagerie instantanée, de l’audio/la vidéo, du partage d’applications, du Web, de/Dial tiers et/Dial de Microsoft.
    
- [Rapport d’activité de participation à des conférences Skype entreprise](conference-participant-activity-report.md) Vous pouvez voir le nombre de messages instantanés, audio/vidéo, du partage d’applications, du Web et de la numérotation des conférences audio.
    
- [Rapport d’activité d’égal à égal Skype entreprise](peer-to-peer-activity-report.md) Vous pouvez visualiser le nombre d’utilisation de la messagerie instantanée, de l’audio/la vidéo, du partage d’applications et du transfert de fichiers par utilisateur.
    
- [Rapport de blocage d’utilisateurs Skype entreprise](users-blocked-report.md) Vous pouvez afficher les utilisateurs de votre organisation qui ont été bloqués et ne peuvent plus passer d’appels RTC.

- [Rapport de pools de minutes RTC Skype entreprise](pstn-minute-pools-report.md) vous pouvez voir le nombre de minutes consommées pendant le mois en cours au sein de votre organisation.

- [Rapport Détails de la session Skype entreprise](session-details-report.md) Vous pouvez afficher des détails sur les expériences d’appel des utilisateurs individuels.
    
## <a name="related-topics"></a>Voir aussi
[Rapports d’activité dans le centre d’administration](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
 
