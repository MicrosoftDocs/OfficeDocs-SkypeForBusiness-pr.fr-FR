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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: La nouvelle Skype Entreprise rapports du Centre d’administration vous présente les activités d’appel et d’audioconférence dans votre organisation. Il vous permet d’drill into reports to give you more granular insight about the activities of each user. Le rapport sur les détails d'utilisation PSTN de Skype Entreprise vous permet par exemple d'afficher le nombre de minutes passées pour des appels entrants ou sortants ainsi que les coûts de ces appels. Vous pouvez afficher les détails d’utilisation PSTN de l’audioconférence, y compris le coût de l’appel, afin de comprendre vos informations d’utilisation et de facturation pour déterminer l’utilisation au sein de votre organisation.
ms.openlocfilehash: 313b6e7528604cfca3b7d7b4a66986337617afa0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58614904"
---
# <a name="pstn-usage-report"></a>Rapport d'utilisation du réseau téléphonique commuté

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

La nouvelle Skype Entreprise rapports  du Centre d’administration vous présente les activités d’appel et d’audioconférence dans votre organisation. Il vous permet d’drill into reports to give you more granular insight about the activities of each user. Le rapport sur les **détails d'utilisation PSTN de Skype Entreprise** vous permet par exemple d'afficher le nombre de minutes passées pour des appels entrants ou sortants ainsi que les coûts de ces appels. Vous pouvez afficher les détails d’utilisation PSTN de l’audioconférence, y compris le coût de l’appel, afin de comprendre vos informations d’utilisation et de facturation pour déterminer l’utilisation au sein de votre organisation.
  
Consultez la vue [d’ensemble des](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) rapports pour découvrir d’autres rapports disponibles.
  
Tout comme les autres rapports de Skype Entreprise, ce rapport vous fournit des détails sur les activités, notamment sur l’utilisation des appels dans votre organisation. Ces informations détaillées sont très utiles pour examiner, planifier et prendre des décisions pour votre entreprise, ainsi que pour définir les [crédits de communication.](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Vous pouvez consulter tous les rapports de Skype Entreprise lorsque vous vous connectez en tant qu’administrateur au Centre d’administration Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Comment obtenir les rapports sur les détails d'utilisation PSTN de Skype Entreprise

![Icône affichant le logo Skype Entreprise](../images/sfb-logo-30x30.png) **Utiliser le Centre d’administration Skype Entreprise**

- Dans le Centre d’administration, > **centres d’administration** Skype Entreprise centre d’administration signale les détails d’utilisation  >    >    >  **PSTN.**
    
    > [!NOTE]
    > En fonction du Microsoft 365 ou Office 365 votre abonnement, vous ne verrez peut-être pas tous les produits et rapports affichés ici.
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>Interpréter le rapport d'utilisation PSTN de Skype Entreprise

Vous pouvez vous connaître l'utilisation PSTN Skype Entreprise d'un utilisateur en consultant chacune des colonnes qui sont affichées.
  
Voici une illustration du rapport.
  
[![Skype Entreprise d’utilisation ](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png) PSTN](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png#lightbox)

***
![Numéro 1](../images/sfbcallout1.png)<br/>Le tableau présente une répartition par utilisateur de toutes les utilisations PSTN. Il vous indique tous les utilisateurs Skype Entreprise qui leur ont été affectés ainsi que leur utilisation PSTN. Vous pouvez ajouter ou supprimer des colonnes dans ce tableau.
*    **L’ID d’appel** est l’ID d’appel d’un appel. Il s’agit d’un identificateur de l’appel utilisé lors de l’appel au support du service Microsoft.
*    **ID de l'utilisateur** est le nom de connexion de l'utilisateur.
*    **Téléphone numéro est** le numéro Skype Entreprise numéro de téléphone qui a reçu l’appel pour les appels entrants ou le numéro composé pour les appels sortants.
*    **L’emplacement de** l’utilisateur est le pays/la région où se trouve l’utilisateur.
*    **L’ID** de l’appelant est le numéro de téléphone de l’appelant (ID de l’appelant) pour les appels entrants, le numéro d’origine de l’appel ou le numéro Skype Entreprise d’origine de l’appel pour les appels sortants.
*    **Le type d’appel** est le type d’appel (sortant ou entrant PSTN) et le type d’appel (par exemple, appel passé par un utilisateur ou conférence audio). Les types d’appels que vous pouvez voir sont les autres : 

     **Types d’appels de plan d’appel** 
     *    **user_in** (l’utilisateur a reçu un appel PSTN entrant) 
     *    **user_out** (l’utilisateur a passé un appel PSTN sortant) 
     *    **user_out_conf** (l’utilisateur a ajouté 2 participants PSTN ou plus à l’appel, par exemple une conférence 3 sens) 
     *    **user_out_transfer** (l’utilisateur a transféré l’appel vers un numéro PSTN) 
     *    **user_out_forwarding** (l’utilisateur a transmis l’appel à un numéro PSTN)

     **Types d’appels d’audioconférence**
     *    **conf_in** (un appel entrant vers le pont de conférence audio). Pour les enregistrements de ce type d’appel, l’utilisateur spécifié dans la colonne **ID** utilisateur correspond à l’organisateur de la réunion.
     *    **conf_out** (appel sortant du pont d’audioconférence, généralement pour ajouter un numéro PSTN à la conférence). Pour les enregistrements de ce type d’appel, l’utilisateur spécifié dans la colonne **ID** utilisateur correspond à l’organisateur de la réunion.

     **Applications de communication unifiées (UCAP)** 
     *    **ucap_in** (appel PSTN entrant vers l’application de lauc, tel que le attendant automatique ou la file d’attente d’appels) 
     *    **ucap_out** (un appel PSTN sortant à partir de l’application de lauc, telle que le attendant automatique ou la file d’attente d’appels)
         > [!NOTE]
         > Les appels transférés vers un utilisateur à partir de l’application de lauc, telle qu’un attendant automatique ou une file d’attente d’appels, ne s’affichent pas dans le rapport d’utilisation PSTN, car ces appels sont des appels audio d’égal à égal (P2P). Vous pouvez accéder aux appels P2P dans le Centre d’administration Skype Entreprise sous « Outils d’analyse des appels > Skype Entreprise » et effectuer une recherche par nom d’utilisateur ou adresse SIP en corrélant l’appel par date/heure et/ou en provenance de la CLID (calling line ID). 

     **Nationaux/Internationaux** vous indique si l’appel placé a été considéré comme national (dans un pays ou une région) ou international (en dehors d’un pays ou d’une région) en fonction de l’emplacement de l’utilisateur. 
*    **L’appel de** destination est le nom de la destination du pays/de la région composé, par exemple, la France, l’Allemagne ou les États-Unis. 
*    **Le type de** numéro de téléphone est le type de numéro de téléphone provenant du numéro de téléphone d’un utilisateur, d’un service ou d’un numéro gratuit.  
*    **Heure de début (UTC)** est l'heure à laquelle l'appel a commencé. 
*    **Durée** indique le temps de connexion de l'appel.  
*    **ConfID est** l’ID de conférence de la conférence audio. 
*    **Le** montant est le montant ou le coût de l’appel facturé sur votre compte. 
*    **Devise** est le type de devise utilisé pour calculer le coût de l’appel. 
*    **La fonctionnalité** est la licence utilisée pour l’appel. Les types de licences que vous pouvez voir sont les autres : 
     *    **MCOPSTNPP** - Crédits de communication <br/> **MCOPSTN1** - Plan d’appels nationaux (plans de 3 000 min pour les États-Unis / 1 200 min pour l’UE) 
     *    **MCOPSTN2** - Forfait d’appels internationaux 
     *    **MCOPSTN5** - Forfait d’appels nationaux (forfait d’appels de 120 min) 
     *    **MCOPSTN6** - Forfait d’appels nationaux (plan d’appels de 240 min) Remarque : Disponibilité limitée
     *    **MCOMEETADD** - Audioconférence
     *    **MCOMEETACPEA** - Audioconférence avec paiement à la minute
     
> [!NOTE]
> Si vous souhaitez exécuter un rapport pour inclure uniquement les appels à la minute qui ne sont pas inclus dans votre abonnement d’appel ou de conférence, filtrez le rapport avec la fonctionnalité « MCOPSTNPP ». Cela permettra d’détailiser tous les appels à la minute.  Pour l’audioconférence avec paiement à la minute, filtrez par « MCOMEETACPEA » au lieu de « MCOPSTNPP ».  

> [!NOTE]
> Il se peut également que vous ne voyez « aucune donnée » dans certains champs. « Aucune donnée » signifie que le champ n’est pas applicable au type ou à la fonctionnalité d’appel. 

> [!NOTE]
> Si vous avez un plan d’appel Telstra ou Softbank, aucun enregistrement des détails des appels n’est présent dans le rapport d’utilisation PSTN. Contactez Telstra ou Softbank pour répondre à vos besoins en matière de rapports. 
***
![Numéro 2](../images/sfbcallout2.png)<br/>Cliquez pour déplacer une colonne vers **Pour regrouper les informations autour d'une colonne en particulier, faites glisser et déplacez l'en-tête de la colonne ici** si vous souhaitez visualiser toutes les données regroupées dans une ou plusieurs colonnes.
 ***

## <a name="exporting-pstn-usage-report"></a>Exporter le rapport d’utilisation PSTN

Cliquer ou appuyer sur le bouton Exporter **vers Excel** vous permet de télécharger le rapport d’utilisation PSTN. Vous pouvez exporter des données jusqu’à un an à partir de la date actuelle, sauf si la réglementation spécifique au pays interdit la rétention des données pendant 12 mois.

Cela exportera les données de tous les utilisateurs et vous permettra de trier et de filtrer plus simplement pour une analyse ultérieure.

Le processus d’exportation peut prendre de quelques secondes à plusieurs minutes, selon la quantité de données. Une fois l’exportation terminée par le serveur, vous recevrez un fichier zip nommé «**Calls.Export.[ `identifier` ] .zip**« , l’identificateur étant un ID unique pour l’exportation, qui peut être utilisé pour résoudre des problèmes.

Si vous avez à la fois des plans d’appels et un routage direct, le fichier exporté peut contenir des données pour les deux produits. Le fichier du rapport d’utilisation PSTN aura le nom de fichier **« PSTN.calls.[ `UTC date` ] .csv**» En plus des fichiers RSTN et du routage direct, l’archive contient le fichier «parameters.json **»,** avec l’plage et les fonctionnalités d’exportation sélectionnées (le cascher).

Le fichier exporté est un fichier de valeurs séparées par des virgules (CSV), conforme à la norme [RFC 4180.](https://tools.ietf.org/html/rfc4180) Le fichier peut être ouvert en même temps que Excel’éditeur conforme aux normes sans nécessiter de transformation.

La première ligne du CSV contient les noms de colonnes.

### <a name="fields-in-the-export"></a>Champs de l’exportation

Le fichier exporté contient d’autres champs qui ne sont pas disponibles dans le rapport en ligne. Ceux-ci peuvent être utilisés pour la résolution des problèmes et l’automatisation des flux de travail.

> [!div class="has-no-wrap"]  
> | #  | Nom | [Type de données (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | Description |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | Identificateur d’appel unique |
> | 1 | ID d’appel | `nvarchar(64)` | Identificateur d’appel. Non garantit que son caractère unique n’est pas garanti |
> | 2 | ID de conférence | `nvarchar(64)` | ID de la conférence audio |
> | 3 | Emplacement de l’utilisateur | `nvarchar(2)` | Code de pays de l’utilisateur, [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | Appelez l’ID d’utilisateur dans Azure Active Directory.<br/> Ces informations utilisateur et les autres utilisateurs seront null/vides pour les types d’appels de bot (ucap_in, ucap_out) |
> | 5 | UPN | `nvarchar(128)` | UserPrincipalName (nom de la signature) dans Azure Active Directory.<br/>Il s’agit généralement de l’adresse SIP de l’utilisateur et de l’adresse de messagerie de l’utilisateur. |
> | 6 | Nom d’affichage de l’utilisateur | `nvarchar(128)` | Nom d’affichage de l’utilisateur |
> | 7 | ID de l’appelant | `nvarchar(128)` | Numéro de l’appel pour les appels entrants ou numéro composé pour les appels sortants. [Format E.164](https://en.wikipedia.org/wiki/E.164) |
> | 8 | Type d'appel | `nvarchar(32)` | Si l’appel était un appel entrant ou sortant PSTN et le type d’appel tel qu’un appel passé par un utilisateur ou une audioconférence |
> | 9 | Type de numéro | `nvarchar(16)` | Le type de numéro de téléphone de l’utilisateur, tel qu’un service de numéro gratuit |
> | 10 | Nationaux/Internationaux | `nvarchar(16)` | Si l’appel était national (dans un pays ou une région) ou international (en dehors d’un pays ou d’une région) en fonction de l’emplacement de l’utilisateur |
> | 11 | Destination Dialed | `nvarchar(64)` | Pays ou région composé |
> | 12 | Numéro de destination | `nvarchar(32)` | Numérotation au format [E.164](https://en.wikipedia.org/wiki/E.164) |
> | 13 | Heure de début | `datetimeoffset` | Heure de début d’appel (UTC, [ISO 8601)](https://en.wikipedia.org/wiki/ISO_8601) |
> | 14 | Heure de fin | `datetimeoffset` | Heure de fin des appels (UTC, [ISO 8601)](https://en.wikipedia.org/wiki/ISO_8601) |
> | 15 | Duration Seconds | `int` | Durée de connexion de l’appel |
> | 16 | Frais de connexion | `numeric(16, 2)` | Prix des frais de connexion |
> | 17 | Charge | `numeric(16, 2)` | Montant ou coût de l’appel facturé sur votre compte |
> | 18 | Devise | `nvarchar(3)` | Type de devise utilisé pour calculer le coût de l’appel[(ISO 4217)](https://en.wikipedia.org/wiki/ISO_4217) |
> | 19 | Fonctionnalité | `nvarchar(32)` | Licence utilisée pour l’appel |

    
## <a name="want-to-see-other-skype-for-business-reports"></a>Autres rapports d'activité Skype Entreprise

- [Skype Entreprise d’activité de l’entreprise](activity-report.md) Vous pouvez consulter le nombre d’utilisations, d’organisation et de participations de vos utilisateurs à des conférences.
    
- [Skype Entreprise d’utilisation de l’appareil](device-usage-report.md) Vous pouvez voir les appareils, y compris les Windows d’exploitation basés sur des systèmes d’exploitation et les appareils mobiles sur lesquels l’application Skype Entreprise est installée et qui l’utilisent pour la messagerie instantanée et les réunions.
    
- [Skype Entreprise activité de l’organisateur de conférences](conference-organizer-activity-report.md) Vous pouvez voir combien de fois vos utilisateurs organisent des conférences qui utilisent la messagerie instantanée, l’audio/la vidéo, le partage d’application, le web, /dial out - tiers et /dial out - Microsoft.
    
- [Skype Entreprise activité de participant à une conférence](conference-participant-activity-report.md) Vous pouvez voir le nombre de conférences audio/vidéo, de messagerie instantanée, de partage d’applications, de web et de mise en conférence audio en cours de participation.
    
- [Skype Entreprise rapport d’activité P2 P2 P2](peer-to-peer-activity-report.md) Vous pouvez voir le nombre d’utilisation de la messagerie instantanée, de l’audio/la vidéo, du partage d’application et du transfert de fichiers par utilisateur.
    
- [Skype Entreprise les utilisateurs bloqués](users-blocked-report.md) Vous pouvez voir les utilisateurs de votre organisation qui ont été bloqués et ne peuvent plus effectuer d’appels PSTN.

- Skype Entreprise des pools de [minutes PSTN](pstn-minute-pools-report.md) vous indiquent le nombre de minutes consommées au cours du mois en cours au sein de votre organisation.

- [Skype Entreprise détails de la session](session-details-report.md) Vous pouvez voir des détails sur les expériences d’appels d’un utilisateur individuel.
    
## <a name="related-topics"></a>Rubriques connexes
[Rapports d’activité dans le Centre d’administration](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
