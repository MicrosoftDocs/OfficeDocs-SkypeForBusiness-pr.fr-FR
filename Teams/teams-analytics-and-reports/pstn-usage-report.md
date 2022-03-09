---
title: Microsoft Teams d’utilisation PSTN
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
MS.collection:
- M365-voice
description: Découvrez comment utiliser le rapport Teams utilisation de la conférence PSTN dans le Centre d’administration Microsoft Teams pour avoir une vue d’ensemble de l’utilisation des appels et de l’audioconférence dans votre organisation.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3c271ee710f84bed5f35b66969ce4970cd21b36a
ms.sourcegitcommit: fe71ecbe35b8adfb9166188923ed1111b3b8e2a1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2022
ms.locfileid: "63388066"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Microsoft Teams d’utilisation PSTN

Le Teams d’utilisation PSTN (Public Switched Telephone Network) dans le Centre d’administration Microsoft Teams donne une vue d’ensemble de l’activité d’appel et d’audioconférence dans votre organisation. Vous pouvez consulter l’activité d’appels détaillée pour les forfaits d’appels si vous utilisez Microsoft comme opérateur de téléphonie et pour le routage direct si vous utilisez votre propre opérateur de téléphonie.

**L’onglet Forfaits** d’appels affiche des informations, notamment le nombre de minutes passées par les utilisateurs pour les appels PSTN entrants et sortants, ainsi que le coût de ces appels. **L’onglet Routage direct** vous présente des informations, dont l’adresse SIP et les heures de début et de fin des appels. Utilisez les informations de ce rapport pour obtenir des informations sur l’utilisation PSTN dans votre organisation et vous aider à examiner, planifier et prendre des décisions professionnelles.

> [!NOTE]
> Si vous avez un plan d’appel Telstra ou Softbank, aucun enregistrement des détails des appels n’est présent dans le rapport d’utilisation PSTN. Contactez Telstra ou Softbank pour répondre à vos besoins en matière de rapports. 

## <a name="view-the-pstn-usage-report"></a>Afficher le rapport d’utilisation PSTN

1. Dans la barre de navigation gauche du Microsoft Teams d’administration, cliquez sur **Analyse & rapports d’utilisation** >  **des rapports**. Sous **l’onglet Afficher les** rapports, sous **Rapport**, sélectionnez **Rapport d’utilisation PSTN**.
2. Sous **Plage de dates**, sélectionnez une plage prédéfinie de 7 ou 28 jours, ou définissez une plage personnalisée, puis sélectionnez **Exécuter le rapport**.

## <a name="interpret-the-report"></a>Interpréter le rapport

### <a name="calling-plans"></a>Forfaits d’appel

   ![Rapport d’utilisation de plans d’appel PSTN dans le Centre d’administration](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png)![Rapport d’utilisation PSTN dans le Centre Microsoft Teams d’administration avec des appels numéroés](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png#lightbox)

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport peut être vu pour les tendances des 7, 28 derniers jours ou une plage de dates personnalisée que vous avez définie. |
|**2**   |Chaque rapport indique la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l'heure de l'activité. |
|**3**   |L’axe X est la plage de dates sélectionnée pour le rapport spécifique. L’axe Y est le nombre total d’appels sur la période sélectionnée. <br>Pointez sur le point à une date donnée pour voir le nombre total d’appels à cette date.  |
|**4**   |Le tableau offre une répartition par appel de l’utilisation PSTN. <ul><li>**L’heure et l’heure (UTC)** sont l’heure de début de l’appel.</li><li>**Le nom d’affichage** est le nom d’affichage de l’utilisateur. Vous pouvez cliquer sur le nom d’affichage pour aller à la page de paramètres de l’utilisateur dans le Microsoft Teams d’administration.</li><li>**Le** nom d’utilisateur est le nom de connexion de l’utilisateur.</li><li>**Téléphone est** le numéro qui a reçu l’appel pour les appels entrants ou le numéro composé pour les appels sortants.</li><li>**Le type d’appel** est le type d’appel (pSTN sortant ou entrant) et le type d’appel (par exemple, appel passé par un utilisateur ou conférence audio). Les types d’appels que vous pouvez voir sont les suivants :<br><br>**Teams types d’appels de l’utilisateur**<ul><li>**user_in** : l’utilisateur a reçu un appel PSTN entrant</li><li>**user_out** : l’utilisateur a passé un appel PSTN sortant</li><li>**user_out_conf** : l’utilisateur a ajouté plusieurs participants PSTN à l’appel, par exemple une conférence à trois.</li><li>**user_out_transfer** : l’utilisateur a transféré l’appel vers un numéro PSTN</li><li>**user_out_forwarding** : l’utilisateur a transmis l’appel à un numéro PSTN</li><li>**conf_in** - appel entrant vers le pont de conférence audio</li><li>**conf_out** : appel sortant du pont de conférence audio généralement pour ajouter un numéro PSTN à la conférence</li><li>**unassigned_in** : un appel PSTN entrant via un plan d’appels vers un numéro non engagé</li></ul><br>**Teams types d’appels des robots**<ul><li>**ucap_in** - appel PSTN entrant vers un robot Teams tel qu’un attendant automatique ou une file d’attente d’appels</li><li>**ucap_out** - Appel RST sortant à partir d’un robot Teams tel que le attendant automatique ou la file d’attente d’appels</li></ul><br><li>**Appelé est** le numéro composé.</li><li>**Le pays ou la région** est composé du pays ou de la région.</li><li>**Appelé depuis** est le numéro qui a passé l’appel.</li><li>**À partir du pays ou de la** région est le pays ou la région à partir de laquelle l’appel a été passé.</li><li>**Le** montant est le montant ou le coût de l’appel facturé sur votre compte. </li><li>**Devise** est le type de devise utilisé pour calculer le coût de l’appel. </li><li>**Durée** indique le temps de connexion de l'appel.</li><li>**Nationaux/Internationaux** vous indique si l’appel était national (dans un pays ou une région) ou international (à l’extérieur d’un pays ou d’une région) en fonction de l’emplacement de l’utilisateur.</li><li>**L’ID d’appel** est l’ID d’appel d’un appel. Il s’agit d’un identificateur de l’appel que vous pouvez utiliser lorsque vous appelez le Support Microsoft.</li><li>**Le type de** numéro de téléphone est le type de numéro de téléphone de l’utilisateur, par exemple un service de numéro gratuit. </li><li>**Le pays ou la région est** le lieu d’utilisation. </li> <li>**L’ID de** conférence est l’ID de conférence de la conférence audio. </li><li>**La fonctionnalité** est la licence utilisée pour l’appel. Les types de licences que vous pouvez voir sont les suivants :<ul><li>**MCOEV, MCOEV_VIRTUALUSER ou MCOEV_VIRTUALUSER_GOV** - Applications vocales telles que le attendant automatique ou les files d’attente d’appels</li><li>**FREECALL** - En cas de problème technique qui nous empêche de tarifr un appel, l’appel est fourni gratuitement et s’affiche avec cette fonctionnalité</li><li>**MCOPSTN1** - Plan d’appels nationaux (plans de 3 000 min POUR les États-Unis / 1 200 min pour l’UE)</li><li>**MCOPSTN2** - Forfait d’appels internationaux</li><li>**MCOPSTN5** - Forfait d’appels nationaux (forfait d’appels de 120 min)</li><li>**MCOPSTN6** - Forfait d’appels nationaux (plan d’appels de 240 min)</li><li>**MCOPSTN8** - Forfait d’appels nationaux 120 min par utilisateur (pas de regroupement entre utilisateurs comme les autres forfaits d’appels)</li><li>**MCOPSTN9** - Forfait d’appels internationaux</li><li>**MCOPSTNCAP** - Zone commune Téléphone</li><li>**MCOPSTNPP** - Crédits de communication</li><li>**MCOMEETADD** - Audioconférence</li><li>**MCOMEETADD_DIALOUT_US** - Audioconférence aux États-Unis et au Canada - Plan d’appels sortants</li><li>**MCOMEETADD_CN_GLOBAL** - Audioconférence pour les utilisateurs autres que la Chine</li><li>**MCOMEETADD_TATA** - Tata Communications Connections</li><li>**MCOMEETACPEA** - Audioconférence - Paiement à la minute </li><li>**MCOMEETACPEA_GOV** - Audioconférence à la minute pour les administrations publiques</li></ul></li></ul> Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau.|
|**5**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
|**6**   |**Sélectionnez Filtrer** pour filtrer le rapport par nom d’utilisateur ou type d’appel. |
|**7**   |**Sélectionnez Plein écran** pour afficher le rapport en mode Plein écran. |
|**8**   |Vous pouvez exporter le rapport dans un fichier CSV à des fin d’analyse en mode hors connexion. Cliquez **sur Exporter vers Excel**, puis sous l’onglet **Téléchargements**, cliquez sur Télécharger  pour télécharger le rapport lorsqu’il est prêt.|

### <a name="direct-routing"></a>Routage direct

   ![Rapport d’utilisation PSTN du routage direct dans le Centre d’administration](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png)![Capture d’écran du rapport d’utilisation PSTN du routage direct dans le Microsoft Teams d’administration avec des appels numéroés](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png#lightbox)

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport peut être vu pour les tendances des 7 ou 28 derniers jours. |
|**2**   |Chaque rapport indique la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l'heure de l'activité. |
|**3**   |L’axe X est la plage de dates sélectionnée pour le rapport spécifique. L’axe Y est le nombre total d’appels sur la période sélectionnée.<br>Pointez sur le point à une date donnée pour voir le nombre total d’appels à cette date.  |
|**4**   |Le tableau offre une répartition par appel de l’utilisation PSTN. <ul><li>**L’heure et l’heure (UTC)** sont l’heure de début de l’appel.</li><li>**Le nom d’affichage** est le nom d’affichage de l’utilisateur. Vous pouvez cliquer sur le nom d’affichage pour afficher la page des paramètres de l’utilisateur dans Microsoft Teams d’administration. Le nom peut également être le nom d’un bot, par exemple, file d’attente d’appels ou Cloud Standard automatique. </li><li>**L’adresse SIP** est l’adresse SIP de l’utilisateur ou d’un robot qui a reçu ou effectué l’appel.</li><li>**Le numéro d’appelant** est le numéro de l’utilisateur ou du robot qui a effectué l’appel. </li><li>**Le numéro de l’appelant** est le numéro de l’utilisateur ou du robot qui a reçu l’appel. Lors d’un appel entrant à un Teams il s’agit de l’utilisateur Teams; sur un appel sortant d’un Teams il s’agit de l’utilisateur PSTN. </li><li>**Le type d’appel** est le type d’appel (pSTN sortant ou entrant) et le type d’appel (par exemple, appel passé par un utilisateur ou conférence audio). Les types d’appels que vous pouvez voir sont les suivants :<br><br>**Teams types d’appels de l’utilisateur**<ul><li>**dr_in** : l’utilisateur a reçu un appel PSTN entrant</li><li>**dr_out** : l’utilisateur a passé un appel PSTN sortant</li><li>**dr_out_user_conf** : l’utilisateur a ajouté un participant PSTN à l’appel</li><li>**user_out_transfer** : l’utilisateur a transféré l’appel vers un numéro PSTN</li><li>**dr_out_user_forwarding** : l’utilisateur a transmis l’appel à un numéro PSTN</li><li>**dr_out_user_transfer** : l’utilisateur a transféré l’appel vers un numéro PSTN</li><li>**dr_emergency_out** : l’utilisateur a effectué un appel d’urgence</li><li>**dr_unassigned_in** : un appel PSTN entrant via un routage direct vers un numéro non engagé</li></ul><br>**Teams types d’appels des robots**<ul><li>**dr_in_ucap** : un appel PSTN entrant vers un robot Teams tel que le attendant automatique ou la file d’attente d’appels</li><li>**dr_out_ucap** - Appel RST sortant à partir d’un robot Teams tel que le attendant automatique ou la file d’attente d’appels</li></ul><br><li>**Appelé est** le numéro de l’utilisateur qui a reçu l’appel.</li><li>L’heure de début **(UTC)** est l’heure à où le proxy SIP a reçu la réponse finale (message SIP « 200 OK ») à partir du SBC d’un appel sortant (Teams/Bot à un utilisateur RTC), ou une fois que le proxy SIP a envoyé l’invitation au saut suivant dans le serveur principal Teams sur un appel entrant (un utilisateur RTC vers un Teams/Bot). </li><li>L’heure d’invitation **(UTC)** est le moment où l’invitation initiale a été envoyée lors d’un appel sortant à partir d’un appel d’utilisateur ou de robot Teams vers le SBC, ou reçue lors d’un appel entrant vers un appel de Teams ou de bot par le composant proxy SIP du routage direct à partir du SBC.</li><li>**L’heure d’échec (UTC)** est l’heure de l’échec de l’appel. Pour les appels en échec uniquement. Le code SIP final, le sous-code Microsoft final et la phrase SIP finale expliquent les raisons de l’échec de l’appel et peuvent vous aider à résoudre les problèmes. </li><li>**L’heure de fin (UTC)** est la durée de l’appel terminée (pour les appels réussis uniquement).</li><li>**Durée** indique le temps de connexion de l'appel.</li><li>**Le type de** numéro de téléphone est le type de numéro de téléphone de l’utilisateur, par exemple un service de numéro gratuit. </li><li>**La dérivation** média indique si la ligne a été activée pour la dérivation média. </li> <li>**Le nom de domaine complet (FQDN) SBC** du contrôleur de session en bordure (SBC) est complet. </li><li>**La région Azure pour les médias est** le centre de données qui a été utilisé comme chemin multimédia dans un appel sans contournement. </li><li>**La région Azure pour le signalisation** est le centre de données utilisé pour la signalisation pour les appels de dérivation et les appels sans contournement. </li><li>**Le type d’événement** est le type d’événement de l’appel. Les appels réussis et les tentatives d’appels en échec sont au rendez-vous. </li><li>**Le code SIP final** est le code avec lequel l’appel s’est terminé.</li><li>**Le sous-code Microsoft final** est un code qui indique des actions spécifiques qui se sont produites.</li><li>**La phrase SIP finale** est la description du code SIP et du sous-code Microsoft.</li><li>**L’ID de corrélation** est un identificateur unique de l’appel que vous pouvez utiliser lorsque vous appelez le Support Microsoft.</li><li>**L’ID de corrélation partagé** est visible uniquement dans le fichier CSV téléchargeable et n’existe pas dans le portail. L’ID de corrélation partagé existe dans au moins deux appels apparentés. Consultez la description détaillée ci-dessous.</li></ul> Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau.|
|**5**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
|**6**   |**Sélectionnez Plein écran** pour afficher le rapport en mode Plein écran. |
|**7**   |**Sélectionnez Exporter vers Excel** pour télécharger les données dans un fichier séparé par des virgules (CSV) à des fins d’analyse en mode hors connexion ou pour les utiliser comme entrées pour votre système de facturation. |

#### <a name="callercallee-fields-considerations"></a>Considérations sur les champs Appelant/Appelant

Selon le sens d’appel, les noms de l’appelant ou de l’appelant peuvent contenir des numéros autres que E164.

Ces champs peuvent proviennent du ou des SBC du client. Il existe trois formats que le fichier SBC peut envoyer au routage direct : nombres E.164, nombres autres que E.164 et chaînes.

- Numéro de téléphone E.164 d’un utilisateur  dispose d’un numéro E.164, et d’un utilisateur qui dispose également d’un numéro E.164. 
- Appel depuis un numéro autre qu’E.164. Un utilisateur d’un PBX tiers interconnecté avec le routage direct effectue un appel à Teams utilisateur. Dans ce cas, le numéro d’appelant peut être n’importe quel numéro autre qu’E.164, par exemple +1001. 
- Un expéditeur de courrier indésirable appelle et ne présente pas de numéro, seulement un nom (par exemple, « Service interne de chiffre d’affaires ». Cette chaîne s’affiche dans les rapports.

#### <a name="about-shared-correlation-id"></a>À propos de l’ID de corrélation partagé

L’ID de corrélation partagée existe uniquement dans le fichier Excel que vous téléchargez et indique que deux appels ou plus sont liés. L’exemple suivant explique les différents scénarios et l’présence d’un ID de corrélation partagée.

1.    Utilisateur PSTN 1 sur un point de terminaison PSTN appelé Teams User 1 sur un client Teams, Dr_In de type d’appel, ID de corrélation 57f28917-42k5-4c0c-9433-79734873f2ac, aucun ID de corrélation partagé.
2.    Teams utilisateur 1 sur un client Teams appelé Utilisateur PSTN 1 sur un point de terminaison PSTN, type d’appel Dr_Out 2c12b8ca-62eb-4c48-b68d-e451f518ff4, sans ID de corrélation partagé.
3.    Utilisateur PSTN 1 sur un point de terminaison PSTN appelé utilisateur 2 Teams sur Teams client, type d’appel Dr_In f45e9a25-9f94-46e7-a457-84f5940efde9, ID de corrélation partagé f45e9a25-9f94-46e7-a457-84f5940efde9.
4.    Appel existant 3 avec ID de corrélation « f45e9a25-9f94-46e7-a457-84f5940efde9 ». Utilisateur PSTN 1 dans un appel avec Teams utilisateur 2. Teams l’utilisateur 2 a transféré (aveugle ou consultatif) un appel à un Teams ou un utilisateur PSTN, type d’appel Dr_Out_User_Transfer 45a1da7c-9e97-481a-8a05-3fe19a9a77e0, ID de corrélation partagé f45e9a25-9f94-46e7-a457-84f5940efde9.

## <a name="exporting-the-reports"></a>Exportation des rapports
Cliquez **sur Exporter vers Excel**, puis sous l’onglet **Téléchargements**, cliquez sur Télécharger  pour télécharger le rapport lorsqu’il est prêt. Le processus d’exportation peut prendre de quelques secondes à plusieurs minutes, selon la quantité de données.

Cela exportera les données de tous les utilisateurs et vous permettra de trier et de filtrer plus simplement pour une analyse ultérieure. Les fichiers exportés contiennent des champs supplémentaires qui ne sont pas disponibles dans le rapport en ligne. Ceux-ci peuvent être utilisés pour la résolution des problèmes et l’automatisation des flux de travail.

 Vous recevrez un fichier zip nommé **« Calls.Export ».`[identifier]`.zip**« , l’identificateur étant un ID unique pour l’exportation qui peut être utilisé pour résoudre des problèmes.

Si vous avez à la fois des plans d’appels et un routage direct, le fichier exporté peut contenir des données pour les deux produits. Le fichier du rapport d’utilisation PSTN aura le nom de **fichier « PSTN.calls.`[UTC date]`.csv**» et routage direct « **DirectRouting.calls.`[UTC date]`.csv**« .

 En plus des fichiers PSTN et de routage direct, l’archive contient les fichiers « **parameters.json** », ainsi que les fonctionnalités et les plages d’exportation sélectionnées.

Les fichiers exportés sont au format CSV (Valeurs séparées par des virgules), conformes à la norme [RFC 4180](https://tools.ietf.org/html/rfc4180) . Les fichiers peuvent être ouverts en Excel’éditeur conforme aux normes sans nécessiter de transformation.

La première ligne du CSV contient les noms de colonnes. Toutes les dates sont au format UTC [et ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) .

### <a name="exported-pstn-usage-report"></a>Rapport d’utilisation PSTN exporté

 Vous pouvez exporter des données jusqu’à un an à partir de la date actuelle, sauf si la réglementation spécifique au pays interdit la rétention des données pendant 12 mois.

> [!div class="has-no-wrap"]  
> | # | Nom | [Type de données (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | Description |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | Identificateur d’appel unique |
> | 1 | ID d’appel | `nvarchar(64)` | Identificateur d’appel. Non garantit que son caractère unique n’est pas garanti |
> | 2 | ID de conférence | `nvarchar(64)` | ID de la conférence audio |
> | 3 | Emplacement de l’utilisateur | `nvarchar(2)` | Code de pays de l’utilisateur, [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | Appelez l’ID d’utilisateur dans Azure Active Directory.<br/> Ces informations utilisateur et les autres utilisateurs seront null/vides pour les types d’appels de bots (ucap_in, ucap_out) |
> | 5 | UPN | `nvarchar(128)` | UserPrincipalName (nom de la signature) dans Azure Active Directory.<br/>Il s’agit généralement de l’adresse SIP de l’utilisateur et de l’adresse de messagerie de l’utilisateur. |
> | 6 | Nom d’affichage de l’utilisateur | `nvarchar(128)` | Nom d’affichage de l’utilisateur |
> | 7 | ID de l’appelant | `nvarchar(128)` | Numéro de l’appel pour les appels entrants ou numéro composé pour les appels sortants. [Format E.164](https://en.wikipedia.org/wiki/E.164) |
> | 8 | Type d'appel | `nvarchar(32)` | Qu’il s’agissait d’un appel RSTN sortant ou entrant et du type d’appel tel qu’un appel passé par un utilisateur ou une conférence audio |
> | 9 | Type de numéro | `nvarchar(16)` | Le type de numéro de téléphone de l’utilisateur, tel qu’un service de numéro gratuit |
> | 10 | Nationaux/Internationaux | `nvarchar(16)` | Si l’appel était national (dans un pays ou une région) ou international (en dehors d’un pays ou d’une région) en fonction de l’emplacement de l’utilisateur |
> | 11 | Destination Dialed | `nvarchar(64)` | Pays ou région composé |
> | 12 | Numéro de destination | `nvarchar(32)` | Numérotation au format [E.164](https://en.wikipedia.org/wiki/E.164) |
> | 13 | Heure de début | `datetimeoffset` | Heure de début de l’appel |
> | 14 | Heure de fin | `datetimeoffset` | Heure de fin d’appel |
> | 15 | Duration Seconds | `int` | Durée de connexion de l’appel |
> | 16 | Frais de connexion | `numeric(16, 2)` | Prix des frais de connexion |
> | 17 | Charge | `numeric(16, 2)` | Montant ou coût de l’appel facturé sur votre compte |
> | 18 | Devise | `nvarchar(3)` | Type de devise utilisé pour calculer le coût de l’appel ([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)) |
> | 19 | Fonctionnalité | `nvarchar(32)` | Licence utilisée pour l’appel |

### <a name="exported-direct-routing-usage-report"></a>Rapport d’utilisation du routage direct exporté

Vous pouvez exporter des données à partir de la date actuelle jusqu’à cinq mois (150 jours), sauf si la réglementation pays/région interdit la rétention des données pour cette période.

> [!div class="has-no-wrap"]  
> | # | Nom | [Type de données (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | Description |
> | :-: | :-: | :-: |:------------------- |
> | 0 | CorrelationId | `uniqueidentifier` | Identificateur d’appel. Plusieurs personnes d’un même appel peuvent partager le même CorrelationId |
> | 1 | AAD ObjectId | `uniqueidentifier` | Appelez l’ID d’utilisateur dans Azure Active Directory.<br/> Ces informations utilisateur et d’autres peuvent être null/vides pour les types d’appels de bots |
> | 2 | UPN | `nvarchar(128)` | UserPrincipalName (nom de la Azure Active Directory) de l’utilisateur ou du robot qui a effectué ou reçu l’appel.<br/>Il s’agit généralement de l’adresse SIP de l’utilisateur et de l’adresse de messagerie de l’utilisateur. |
> | 3 | Nom d’affichage | `nvarchar(128)` | Nom d’un utilisateur ou d’un robot d’appel (par exemple, File d’attente ou Appel Standard automatique) tel que Centre d'administration Microsoft 365 |
> | 4 | Pays utilisateur | `nvarchar(2)` | Code de pays de l’utilisateur, [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 5 | Heure d’invitation | `datetimeoffset` | Lorsque l’invitation initiale est envoyé de l’appel sortant d’un utilisateur ou d’un robot à Teams vers le SBC, ou reçu en entrant vers Teams ou un appel de bot par le composant proxy SIP du routage direct à partir du SBC |
> | 6 | Heure de début | `datetimeoffset` | Heure à quel moment le proxy SIP a reçu la réponse finale (message SIP « 200 OK ») à partir du serveur SBC en cours sortant (Teams/Bot à un utilisateur PSTN), ou après que le proxy SIP a envoyé l’invitation au saut suivant dans Teams backend on inbound call (PSTN User to a Teams/Bot).<br/>Pour les appels en absence et sans réponse, cela peut être égal à l’heure de l’invitation ou de l’échec |
> | 7 | Heure d’échec | `datetimeoffset` | Existe uniquement pour les appels en échec (pas entièrement établis) |
> | 8 | Heure de fin | `datetimeoffset` | Existe uniquement pour les appels réussis (entièrement établis). Heure à la fin de l’appel |
> | 9 | Durée (secondes) | `int` | Durée de l’appel |
> | 10 | Opération réussie | `nvarchar(3)` | Oui/Non. Succès ou tentative |
> | 11 | Numéro de l’appelant | `nvarchar(32)` | Numéro de l’utilisateur ou du robot ayant effectué l’appel. Lors de l’appel entrant à un utilisateur d’équipe, il sera un utilisateur PSTN. Dans le cas d’un appel sortant d’un Teams il s’agit du Teams d’utilisateur |
> | 12 | Numéro de l’appelant | `nvarchar(32)` | Numéro de l’utilisateur ou du robot ayant reçu l’appel. Lors de l’appel entrant à un utilisateur d’équipe, il sera l’utilisateur Teams, sortant de Teams’appel d’utilisateur sera l’utilisateur PSTN |
> | 13 | Type d’appel | `nvarchar(32)` | Type et sens d’appel |
> | 14 | Région Azure pour les médias | `nvarchar(8)` | Le centre de données utilisé pour le chemin multimédia dans un appel sans contournement |
> | 15 | Région Azure pour le signalisation | `nvarchar(8)` | Le centre de données utilisé pour le signalisation pour les appels de dérivation et les appels sans contournement |
> | 16 | Code SIP final | `int` | Code avec lequel l’appel a pris fin, [RFC 3261](https://tools.ietf.org/html/rfc3261) |
> | 17 | Sous-code Microsoft final | `int` | En plus des codes SIP, Microsoft possède ses propres sous-codes qui indiquent le problème spécifique |
> | 18 | Phrase SIP finale | `nvarchar(256)` | Description du code SIP et du sous-code Microsoft |
> | 19 | SBC FQDN | `nvarchar(64)` | Nom de domaine complet du contrôleur de session en bordure |
> | 20 | Contournement de média | `nvarchar(3)` | Oui/Non. Indique si la ligne a été activée pour la dérivation média |
> | 21 | ID de corrélation partagé | `uniqueidentifier` | Indique que deux appels ou plus sont liés |


## <a name="related-topics"></a>Sujets associés

- [Analyses et rapports Teams](teams-reporting-reference.md)
- [Rapport d’appel PSTN dans Microsoft Graph](/graph/api/callrecords-callrecord-getpstncalls?view=graph-rest-1.0&tabs=http)
- [Rapport de routage direct dans Microsoft Graph](/graph/api/callrecords-callrecord-getdirectroutingcalls?view=graph-rest-1.0&tabs=http)
