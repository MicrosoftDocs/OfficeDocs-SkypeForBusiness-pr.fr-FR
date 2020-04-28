---
title: Rapport utilisation RTC de Microsoft teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Découvrez comment utiliser le rapport d’utilisation RTC de Microsoft teams dans le centre d’administration de Microsoft teams pour avoir une vue d’ensemble de l’utilisation des fonctionnalités d’appel et de l’audioconférence au sein de votre organisation.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 411cf551697bd1fdd0902dc2d906e1c7752cd27d
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904299"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Rapport utilisation RTC de Microsoft teams

Le rapport utilisation RTC de Microsoft teams dans le centre d’administration Microsoft teams vous donne un aperçu de l’activité des appels et de l’audioconférence au sein de votre organisation. Vous pouvez afficher les appels détaillés pour les offres d’appels si vous utilisez Microsoft comme opérateur de téléphonie et pour le routage direct si vous utilisez votre propre opérateur de téléphonie.

L’onglet **forfaits** d’appels affiche des informations telles que le nombre de minutes passées par les utilisateurs dans les appels RTC entrants et sortants et le coût de ces appels. L’onglet **routage direct** affiche des informations telles que l’adresse SIP et les heures de début et de fin de l’appel. Les informations contenues dans ce rapport vous permettent de vous familiariser avec l’utilisation RTC au sein de votre organisation et vous aident à examiner, planifier et prendre des décisions commerciales.

## <a name="view-the-pstn-usage-report"></a>Afficher le rapport d’utilisation PSTN

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur **analyse &** > rapports d'**utilisation**des rapports. Dans l’onglet **afficher les rapports** , sous **rapport**, sélectionnez **rapport d’utilisation PSTN**.
2. Sous **plage de dates**, sélectionnez une plage de 7 ou 28 jours prédéfinie, ou définissez une plage personnalisée, puis sélectionnez **exécuter un rapport**.

## <a name="interpret-the-report"></a>Interpréter le rapport

### <a name="calling-plans"></a>Forfaits d’appel

![Capture d’écran du rapport sur l’utilisation RTC des plans d’appel dans le centre d’administration](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png "Rapport d’utilisation RTC dans le centre d’administration Microsoft teams avec des légendes numérotées")

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport peut être consulté pour les tendances au cours des 7 derniers jours, 28 jours ou une plage de dates personnalisée que vous avez définie |
|**2**   |Date de génération de chaque rapport. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l'heure de l'activité. |
|**3**   |L’axe X représente la plage de dates sélectionnée pour ce rapport particulier. L’axe Y représente le nombre total d’appels sur la période sélectionnée. <br>Pointez sur le point d’une date donnée pour afficher le total des appels à cette date.  |
|**4**   |Le tableau présente une répartition de l’utilisation RTC par appel. <ul><li>**Time horodatage (UTC)** est l’heure à laquelle l’appel a commencé.</li><li>**Nom complet** est le nom d’affichage de l’utilisateur. Vous pouvez cliquer sur le nom d’affichage pour accéder à la page de paramètres de l’utilisateur dans le centre d’administration Microsoft Teams.</li><li>Nom **d'** utilisateur est le nom de connexion de l’utilisateur.</li><li>**Numéro de téléphone** est le numéro qui a reçu l’appel pour les appels entrants ou le numéro numéroté pour les appels sortants.</li><li>**Type d’appel** indique si l’appel était un appel RTC entrant ou sortant et le type d’appel passé par un utilisateur ou une conférence audio. Les types d’appels que vous pouvez voir sont les suivants :<br><br>**Types d’appels utilisateur teams**<ul><li>**user_in** : l’utilisateur a reçu un appel RTC entrant.</li><li>**user_out** : l’utilisateur a placé un appel RTC sortant</li><li>**user_out_conf** -l’utilisateur a ajouté deux participants PSTN ou plus à l’appel, par exemple une conférence téléphonique à trois directions.</li><li>**user_out_transfer** : l’utilisateur a transféré l’appel vers un numéro PSTN.</li><li>**user_out_forwarding** : l’utilisateur a renvoyé l’appel vers un numéro PSTN.</li><li>**conf_in** -appel entrant vers le pont de conférence audio</li><li>**conf_out** -un appel sortant provenant du pont d’audioconférence pour ajouter un numéro PSTN à la Conférence</li></ul><br>**Types d’appels de robots teams**<ul><li>**ucap_in** -un appel RTC entrant au bot Teams, tel que le standard automatique ou la file d’attente d’appels</li><li>**ucap_out** -un appel RTC sortant d’un bot de Microsoft Teams, tel que le standard automatique ou la file d’attente d’appels</li></ul><br><li>**Appelé à** correspond au numéro composé.</li><li>Le **pays ou la région est le** pays ou la région.</li><li>**Appelé from** est le numéro qui a placé l’appel.</li><li>Le **pays ou la région est le** pays ou la région depuis lequel l’appel a été placé.</li><li>**Frais** est la somme d’argent ou le coût de l’appel débité sur votre compte. </li><li>**Devise** correspond au type de devise utilisé pour calculer le coût de l’appel. </li><li>**Durée** indique le temps de connexion de l'appel.</li><li>**National/international** vous indique si l’appel était national (dans un pays ou une région) ou international (à l’extérieur d’un pays ou d’une région) en fonction de l’emplacement de l’utilisateur.</li><li>**ID d’appel** est l’ID d’appel d’un appel. Il s’agit d’un identificateur que vous pouvez utiliser lorsque vous appelez le support technique de Microsoft.</li><li>**Type de numéro** est le type de numéro de téléphone de l’utilisateur, par exemple un service de numéro gratuit. </li><li>Le **pays ou la région** correspond au lieu d’utilisation. </li> <li>**ID de conférence** est l’ID de conférence de la conférence audio. </li><li>**Capability** est la licence utilisée pour l’appel. Les types de licences que vous pouvez voir sont les suivants :<ul><li>**MCOPSTNPP** -crédits de communication</li><li>**MCOPSTN1** -forfait d’appels nationaux (3000 min US/1200 min Europe)</li><li>**MCOPSTN2** -forfait d’appels internationaux</li><li>**MCOPSTN5** -forfait d’appels nationaux (forfait d’appels min 120)</li><li>**MCOPSTN6** -forfait d’appels nationaux (forfait d’appels min 240)</li><li>**MCOMEETADD** -audioconférence</li><li>**MCOMEETACPEA** -audioconférence à la minute</li></ul></li></ul> Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau.|
|**5**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
|**6**   |Sélectionner **filtre** pour filtrer le rapport par nom d’utilisateur ou type d’appel |
|**7**   |Pour afficher le rapport en mode plein écran, sélectionnez **plein écran** . |
|**version8**   |Vous pouvez exporter le rapport dans un fichier CSV pour une analyse hors connexion. Cliquez sur **Exporter vers Excel**, puis sous l’onglet **téléchargements** , cliquez sur **Télécharger** pour télécharger le rapport dès qu’il est prêt.|

### <a name="direct-routing"></a>Routage direct

![Capture d’écran du rapport de rapport d’utilisation RTC du routage direct dans le centre d’administration](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png "Capture d’écran du rapport sur l’utilisation RTC du routage direct dans le centre d’administration Microsoft teams avec des légendes numérotées")

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport peut être consulté pour les tendances au cours des 7, ou 28 derniers jours. |
|**2**   |Date de génération de chaque rapport. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l'heure de l'activité. |
|**3**   |L’axe X représente la plage de dates sélectionnée pour ce rapport particulier. L’axe Y représente le nombre total d’appels sur la période sélectionnée.<br>Pointez sur le point d’une date donnée pour afficher le total des appels à cette date.  |
|**4**   |Le tableau présente une répartition de l’utilisation RTC par appel. <ul><li>**Time horodatage (UTC)** est l’heure à laquelle l’appel a commencé.</li><li>**Nom complet** est le nom d’affichage de l’utilisateur. Vous pouvez cliquer sur le nom d’affichage pour accéder à la page des paramètres de l’utilisateur dans le centre d’administration Microsoft Teams. Il peut également s’agir du nom d’un bot (par exemple, la file d’attente d’appels ou le standard automatique du Cloud). </li><li>**Adresse SIP** correspond à l’adresse SIP de l’utilisateur ou du bot ayant reçu ou passé l’appel.</li><li>**Numéro** de l’appelant est le numéro de l’utilisateur ou du bot qui a émis l’appel. </li><li>**Numéro de téléphone** est le numéro de l’utilisateur ou du bot ayant reçu l’appel. Lors d’un appel entrant à un utilisateur de teams, il s’agit de l’utilisateur de teams, lors d’un appel sortant d’un utilisateur de teams, il s’agit de l’utilisateur RTC. </li><li>**Type d’appel** indique si l’appel était un appel RTC entrant ou sortant et le type d’appel passé par un utilisateur ou une conférence audio. Les types d’appels que vous pouvez voir sont les suivants :<br><br>**Types d’appels utilisateur teams**<ul><li>**dr_in** : l’utilisateur a reçu un appel RTC entrant</li><li>**dr_out** : l’utilisateur a placé un appel RTC sortant</li><li>**dr_out_user_conf** -l’utilisateur a ajouté un participant PSTN à l’appel</li><li>**user_out_transfer** : l’utilisateur a transféré l’appel vers un numéro PSTN.</li><li>**dr_out_user_forwarding** : l’utilisateur a renvoyé l’appel vers un numéro PSTN.</li><li>**dr_out_user_transfer** : l’utilisateur a transféré l’appel vers un numéro PSTN.</li><li>**dr_emergency_out** : l’utilisateur a émis un appel d’urgence</li></ul><br>**Types d’appels de robots teams**<ul><li>**dr_in_ucap** -un appel RTC entrant vers un bot de Microsoft Teams, tel que le standard automatique ou la file d’attente d’appels</li><li>**dr_out_ucap** -un appel RTC sortant d’un bot de Microsoft Teams, tel que le standard automatique ou la file d’attente d’appels</li></ul><br><li>**Appelé à** correspond au numéro de l’utilisateur qui a reçu l’appel.</li><li>**Heure de début (UTC)** est l’heure à laquelle le proxy SIP a reçu la réponse finale (message SIP "200 OK") de la SBC sur un appel sortant (Team/bot à un utilisateur RTC), ou après l’envoi de l’invitation au tronçon suivant du serveur principal Teams (utilisateur RTC à une équipe/bot). </li><li>**Temps d’invitation (UTC)** est l’heure à laquelle l’invitation initiale a été envoyée lors d’un appel sortant d’un utilisateur ou d’un appel de robots d’équipe à l’SBC, ou reçu lors d’un appel entrant à un appel d’équipe ou de robot par le composant proxy SIP du routage direct à partir de l’SBC.</li><li>**Temps d’échec (UTC)** est l’heure à laquelle l’appel a échoué. Pour les appels en échec uniquement. Le code SIP final, le sous-code final de Microsoft et la phrase SIP finale fournissent les raisons pour lesquelles l’appel a échoué et peut vous aider à résoudre les problèmes. </li><li>**Heure de fin (UTC)** est l’heure de fin de l’appel (pour les appels réussis uniquement).</li><li>**Durée** indique le temps de connexion de l'appel.</li><li>**Type de numéro** est le type de numéro de téléphone de l’utilisateur, par exemple un service de numéro gratuit. </li><li>**Contournement de média** indique si le Trunk a été activé pour la dérivation multimédia. </li> <li>Le **FQDN SBC** est le nom de domaine complet (FQDN) du contrôleur de bordure de session (SBC). </li><li>La **région Azure pour le média** est le centre de données utilisé comme chemin multimédia dans un appel sans contournement. </li><li>La **région Azure pour la signalisation** est le centre de données utilisé pour le signalement pour les appels de contournement et de non-contournement. </li><li>**Event type** est le type d’événement de l’appel. Vous verrez réussite pour les appels réussis et tentez d’essayer les appels en échec. </li><li>Le **code SIP final** correspond au code avec lequel l’appel a été interrompu.</li><li>Le sous- **code final de Microsoft** est un code qui indique des actions spécifiques qui se sont produites.</li><li>**Dernière phrase SIP** correspond à la description du code SIP et du sous-code Microsoft.</li><li>**ID de corrélation** est un identificateur unique de l’appel que vous pouvez utiliser lorsque vous appelez le support Microsoft.</li><li>L' **ID de corrélation partagé** est uniquement visible dans le fichier CSV téléchargeable et n’existe pas dans le portail. L’ID de corrélation partagée existe au moins deux appels liés. Veuillez consulter la description détaillée ci-dessous.</li></ul> Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau.|
|**5**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
|**6**   |Pour afficher le rapport en mode plein écran, sélectionnez **plein écran** . |
|**7**   |Sélectionnez **Exporter vers Excel** pour télécharger les données dans un fichier séparé par des virgules (CSV) pour une analyse hors connexion ou pour l’utiliser comme entrée pour votre système de facturation. |

#### <a name="callercallee-fields-considerations"></a>Considérations relatives aux champs appelant et appelé

En fonction du sens de l’appel, le nom de l’appelant ou du visiteur peut contenir des numéros non-E164.

Ces champs peuvent provenir du ou des SBC du client. Il existe trois formats que l’SBC peut envoyer au routage direct : E. 164, des nombres non-E. 164 et des chaînes.

- E. 164 numéro de téléphone d’un utilisateur possédant un numéro E. 164 à un utilisateur qui possède également un numéro E. 164. 
- Appelez à partir d’un numéro non-E. 164. Un utilisateur d’un système PBX tiers connecté avec le routage direct effectue un appel à l’utilisateur d’équipes. Dans le cas présent, le numéro d’appelant peut être n’importe quel numéro non E. 164, par exemple + 1001. 
- Un expéditeur de courrier indésirable et ne présente pas de numéro, ce n’est qu’un nom (par exemple, « service de revenu interne »). Cette chaîne s’affichera dans les rapports.

#### <a name="about-shared-correlation-id"></a>À propos de l’ID de corrélation partagée

L’ID de corrélation partagée existe uniquement dans le fichier Excel exporté que vous téléchargez et indique que deux appels ou plus sont liés. Ce qui suit décrit les différents scénarios, et en présence d’ID de corrélation partagés.

1.    Utilisateur RTC 1 sur un point de terminaison PSTN appelé teams 1 sur le client Teams, type d’appel Dr_In, ID de corrélation 57f28917-42k5-4c0c-9433-79734873f2ac, aucun ID de corrélation partagée.
2.    Utilisateur teams 1 sur le client teams appelé utilisateur RTC 1 sur un point de terminaison PSTN, type d’appel Dr_Out 2c12b8ca-62eb-4c48-B68D-e451f518ff4, aucun ID de corrélation partagée.
3.    Utilisateur RTC 1 sur un point de terminaison PSTN appelé utilisateur d’équipe 2 sur le client Teams, type d’appel Dr_In f45e9a25-9f94-46e7-a457-84f5940efde9, ID de corrélation partagée f45e9a25-9f94-46e7-a457-84f5940efde9.
4.    Appel existant 3 avec ID de corrélation « f45e9a25-9f94-46e7-a457-84f5940efde9 ». Utilisateur RTC 1 en communication avec l’utilisateur teams 2. Utilisateur teams 2 a transféré (aveugle ou consultative) un appel vers teams ou un utilisateur RTC, type d’appel Dr_Out_User_Transfer 45a1da7c-9E97-481a-8a05-3fe19a9a77e0, ID de corrélation partagée f45e9a25-9f94-46e7-a457-84f5940efde9.

## <a name="exporting-the-reports"></a>Exportation des rapports
Cliquez sur **Exporter vers Excel**, puis sous l’onglet **téléchargements** , cliquez sur **Télécharger** pour télécharger le rapport dès qu’il est prêt. Le processus d’exportation peut durer de quelques secondes à quelques minutes, en fonction de la quantité de données.

Cela exportera les données de tous les utilisateurs et vous permettra de trier et de filtrer plus simplement pour une analyse ultérieure. Les fichiers exportés contiennent d’autres champs qui ne sont pas disponibles dans le rapport en ligne. Celles-ci peuvent être utilisées pour résoudre les problèmes et les flux de travail automatisés.

 Vous recevrez un fichier zip intitulé «**appels. Export.`[identifier]`.. Code postal**, avec l’identificateur qui est un ID unique pour l’exportation qui peut être utilisé pour la résolution des problèmes.

Si vous avez les deux plans d’appel et le routage direct, le fichier exporté risque de contenir des données pour les deux produits. Le fichier de rapport d’utilisation RTC dispose du nom de fichier «**PSTN. Calls`[UTC date]`». CSV**» et routage directe «**DirectRouting. Calls`[UTC date]`.. CSV**».

 En plus des fichiers RTC et du routage direct, l’archive contient le fichier «**Parameters. JSON**», avec la plage de valeurs et les capacités d’exportation sélectionnées.

Les fichiers exportés sont au format de valeurs séparées par des virgules (CSV), conforme à la norme [RFC 4180](https://tools.ietf.org/html/rfc4180) . Les fichiers peuvent être ouverts dans Excel ou tout autre éditeur compatible standard sans avoir besoin de transformations.

La première ligne du fichier CSV contient les noms des colonnes. Toutes les dates sont au format UTC et [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) .

### <a name="exported-pstn-usage-report"></a>Rapport d’utilisation RTC exporté

 Vous pouvez exporter des données vers un an au maximum à partir de la date actuelle, sauf si la législation spécifique du pays interdit la conservation des données pour 12 mois.

| # | Nom | [Type de données (SQL Server)](https://docs.microsoft.com/sql/t-sql/data-types/data-types-transact-sql) | Description |
| :-: | :-: | :-: |:------------------- |
| 0,4 | UsageId | `uniqueidentifier` | Identificateur d’appel unique |
| 1 | ID d’appel | `nvarchar(64)` | Identifiant de l’appel. Il n’est pas garanti qu’il soit unique. |
| 2 | ID de conférence | `nvarchar(64)` | ID de la conférence audio |
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
| n°13 | Heure de début | `datetimeoffset` | Heure de début de l’appel |
| 14 | Heure de fin | `datetimeoffset` | Heure de fin de l’appel |
| 0,15 | Secondes de la durée | `int` | Durée de connexion de l’appel |
| Seiz | Frais de connexion | `numeric(16, 2)` | Prix des frais de connexion |
| Play | Frais | `numeric(16, 2)` | Montant de l’argent ou frais de l’appel facturé sur votre compte. |
| 19 | Devise | `nvarchar(3)` | Type de devise utilisé pour le calcul du coût de l’appel ([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)) |
| 19,6 | Fonctionnalité | `nvarchar(32)` | La licence utilisée pour l’appel |

### <a name="exported-direct-routing-usage-report"></a>Rapport d’utilisation du routage direct exporté

Vous pouvez exporter les données jusqu’à cinq mois (150 jours) à partir de la date actuelle, sauf si la réglementation applicable au pays interdit la conservation des données pour cette période.

| # | Nom | [Type de données (SQL Server)](https://docs.microsoft.com/sql/t-sql/data-types/data-types-transact-sql) | Description |
| :-: | :-: | :-: |:------------------- |
| 0,4 | Corrélation | `uniqueidentifier` | Identificateur d’appel unique |
| 1 | Adresse SIP | `nvarchar(128)` | Adresse de l’utilisateur ou du robot ayant passé ou reçu l’appel.<br/>Notez qu’il s’agit réellement de UserPrincipalName (UPN, nom de connexion) dans Azure Active Directory, qui est généralement la même que l’adresse SIP |
| 2 | Nom d’affichage | `nvarchar(128)` | Le nom d’un utilisateur ou d’un bot appelant (par exemple, une file d’attente d’appels ou un standard automatique) défini dans le centre d’administration Microsoft 365 |
| 3 | Pays de l’utilisateur | `nvarchar(2)` | Code pays de l’utilisateur, [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
| 4 | Heure d’invitation | `datetimeoffset` | Lorsque l’invitation initiale envoie un appel sortant à partir d’un utilisateur teams ou d’un appel de robot vers l’SBC, ou est reçu sur entrant en équipe ou à l’appel bot par le composant proxy SIP du routage direct à partir de l’SBC |
| 5 | Heure de début | `datetimeoffset` | Temps pendant lequel le proxy SIP a reçu la réponse finale (message SIP "200 OK") de l’SBC sur sortant (Team/bot vers un utilisateur RTC), ou après l’envoi de l’invitation au tronçon suivant du serveur principal d’équipes sur l’appel entrant (utilisateur RTC à une équipe/bot).<br/>Pour les appels en échec et en sans réponse, il peut s’agir d’un temps d’invitation ou d’échec. |
| 6 | Temps d’échec | `datetimeoffset` | Existe uniquement pour les appels en échec (non entièrement établis) |
| 7 | Heure de fin | `datetimeoffset` | Existe uniquement pour les appels réussis (entièrement établis). Heure de fin de l’appel |
| version8 | Durée (secondes) | `int` | Durée de l’appel |
| 09 | Opération réussie | `nvarchar(3)` | Oui/non. Réussite ou tentative |
| 0,10 | Numéro de l’appelant | `nvarchar(32)` | Numéro de l’utilisateur ou du robot qui a émis l’appel. Lors de l’appel entrant vers un utilisateur d’équipe, il s’agit d’un utilisateur RTC, sur sortant de l’appel d’équipes, il sera le numéro d’utilisateur de teams. |
| midi | Numéro de l’appelant | `nvarchar(32)` | Numéro de l’utilisateur ou du robot ayant reçu l’appel. Lors de l’appel entrant vers un utilisateur d’équipe, il s’agit de l’utilisateur de teams, dans le cadre de l’appel sortant de l’utilisateur Teams, il s’agit de l’utilisateur RTC |
| n°13 | Type d’appel | `nvarchar(32)` | Type d’appel et direction |
| 14 | Région Azure pour éléments multimédias | `nvarchar(8)` | Centre de fichiers utilisé pour le chemin d’accès multimédia dans un appel sans contournement |
| 0,15 | Région Azure pour signalisation | `nvarchar(8)` | Centre de communications utilisé pour le signalement pour les appels de contournement et de non-contournement |
| Seiz | Code SIP final | `int` | Code avec lequel l’appel a été interrompu, [RFC 3261](https://tools.ietf.org/html/rfc3261) |
| Play | Sous-code final de Microsoft | `int` | Outre les codes SIP, Microsoft dispose de propres sous-codes indiquant un problème spécifique. |
| 19 | Phrase SIP finale | `nvarchar(256)` | Description du code SIP et du sous-code Microsoft |
| 19,6 | NOM DE DOMAINE COMPLET SBC | `nvarchar(64)` | Nom de domaine complet du contrôleur de bordure de session |
| CX3-20 | Contournement de média | `nvarchar(3)` | Oui/non. Indique si le Trunk a été activé pour la dérivation multimédia ou non. |
| vingt | ID de corrélation partagée | `uniqueidentifier` | Indique que deux appels ou plus sont liés |


## <a name="related-topics"></a>Voir aussi

- [Analyses et rapports Teams](teams-reporting-reference.md)
