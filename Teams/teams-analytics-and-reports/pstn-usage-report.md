---
title: Rapport utilisation RTC de Microsoft teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Découvrez comment utiliser le rapport d’utilisation RTC de Microsoft teams dans le centre d’administration de Microsoft teams pour avoir une vue d’ensemble de l’utilisation des fonctionnalités d’appel et de l’audioconférence au sein de votre organisation.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c91530af745a287198e99dbb83cd39257d978452
ms.sourcegitcommit: 4c763a3824e6a2271d98a46d25a03c8f04ee2f74
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2019
ms.locfileid: "39257433"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Rapport utilisation RTC de Microsoft teams

Le rapport utilisation RTC de Microsoft teams dans le centre d’administration Microsoft teams vous donne un aperçu de l’activité des appels et de l’audioconférence au sein de votre organisation. Vous pouvez afficher les appels détaillés pour les offres d’appels si vous utilisez Microsoft comme opérateur de téléphonie et pour le routage direct si vous utilisez votre propre opérateur de téléphonie.

L’onglet **forfaits** d’appels affiche des informations telles que le nombre de minutes passées par les utilisateurs dans les appels RTC entrants et sortants et le coût de ces appels. L’onglet **routage direct** affiche des informations telles que l’adresse SIP et les heures de début et de fin de l’appel. Les informations contenues dans ce rapport vous permettent de vous familiariser avec l’utilisation RTC au sein de votre organisation et vous aident à examiner, planifier et prendre des décisions commerciales.

## <a name="view-the-report"></a>Afficher le rapport

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
|**4**   |Le tableau présente une répartition de l’utilisation RTC par appel. <ul><li>**Time horodatage (UTC)** est l’heure à laquelle l’appel a commencé.</li><li>**Nom complet** est le nom d’affichage de l’utilisateur. Vous pouvez cliquer sur le nom d’affichage pour accéder à la page de paramètres de l’utilisateur dans le centre d’administration Microsoft Teams.</li><li>Nom **d'** utilisateur est le nom de connexion de l’utilisateur.</li><li>**Numéro de téléphone** est le numéro qui a reçu l’appel pour les appels entrants ou le numéro numéroté pour les appels sortants.</li><li>**Type d’appel** indique si l’appel était un appel RTC entrant ou sortant et le type d’appel passé par un utilisateur ou une conférence audio. Les types d’appels que vous pouvez voir sont les suivants :<br><br>**Types d’appels utilisateur teams**<ul><li>**user_in** : l’utilisateur a reçu un appel RTC entrant.</li><li>**user_out** : l’utilisateur a placé un appel RTC sortant</li><li>**user_out_conf** -l’utilisateur a ajouté deux participants PSTN ou plus à l’appel, par exemple une conférence téléphonique à trois directions.</li><li>**user_out_transfer** : l’utilisateur a transféré l’appel vers un numéro PSTN.</li><li>**user_out_forwarding** : l’utilisateur a renvoyé l’appel vers un numéro PSTN.</li><li>**conf_in** -appel entrant vers le pont de conférence audio</li><li>**conf_out** -un appel sortant provenant du pont d’audioconférence pour ajouter un numéro PSTN à la Conférence</li></ul><br>**Types d’appels de robots teams**<ul><li>**ucap_in** -un appel RTC entrant au bot Teams, tel que le standard automatique ou la file d’attente d’appels</li><li>**ucap_out** -un appel RTC sortant d’un bot de Microsoft Teams, tel que le standard automatique ou la file d’attente d’appels</li></ul><br><li>**Appelé à** correspond au numéro composé.</li><li>Le **pays ou la région est le** pays ou la région.</li><li>**Appelé from** est le numéro qui a placé l’appel.</li><li>Le **pays ou la région est le** pays ou la région depuis lequel l’appel a été placé.</li><li>**Frais** est la somme d’argent ou le coût de l’appel débité sur votre compte. </li><li>**Devise** correspond au type de devise utilisé pour calculer le coût de l’appel. </li><li>**Durée** indique le temps de connexion de l'appel.</li><li>**National/international** vous indique si l’appel était national (dans un pays ou une région) ou international (à l’extérieur d’un pays ou d’une région) en fonction de l’emplacement de l’utilisateur.</li><li>**ID d’appel** est l’ID d’appel d’un appel. Il s’agit d’un identificateur unique de l’appel que vous pouvez utiliser lorsque vous appelez le support technique de Microsoft.</li><li>**Type de numéro** est le type de numéro de téléphone de l’utilisateur, par exemple un service de numéro gratuit. </li><li>Le **pays ou la région** correspond au lieu d’utilisation. </li> <li>**ID de conférence** est l’ID de conférence de la conférence audio. </li><li>**Capability** est la licence utilisée pour l’appel. Les types de licences que vous pouvez voir sont les suivants :<ul><li>**MCOPSTNPP** -crédits de communication</li><li>**MCOPSTN1** -forfait d’appels nationaux (3000 min US/1200 min Europe)</li><li>**MCOPSTN2** -forfait d’appels internationaux</li><li>**MCOPSTN5** -forfait d’appels nationaux (forfait d’appels min 120)</li><li>**MCOPSTN6** -forfait d’appels nationaux (forfait d’appels min 240)</li><li>**MCOMEETADD** -audioconférence</li><li>**MCOMEETACPEA** -audioconférence à la minute</li></ul></li></ul> Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau.|
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
|**4**   |Le tableau présente une répartition de l’utilisation RTC par appel. <ul><li>**Time horodatage (UTC)** est l’heure à laquelle l’appel a commencé.</li><li>**Nom complet** est le nom d’affichage de l’utilisateur. Vous pouvez cliquer sur le nom d’affichage pour accéder à la page des paramètres de l’utilisateur dans le centre d’administration Microsoft Teams. Il peut également s’agir du nom d’un bot (par exemple, la file d’attente d’appels ou le standard automatique du Cloud). </li><li>**Adresse SIP** correspond à l’adresse SIP de l’utilisateur ou du bot ayant reçu ou passé l’appel.</li><li>**Numéro** de l’appelant est le numéro de l’utilisateur ou du bot qui a émis l’appel. </li>><li>**Numéro de téléphone** est le numéro de l’utilisateur ou du bot ayant reçu l’appel. Lors d’un appel entrant à un utilisateur de teams, il s’agit de l’utilisateur de teams, lors d’un appel sortant d’un utilisateur de teams, il s’agit de l’utilisateur RTC. </li><li>**Type d’appel** indique si l’appel était un appel RTC entrant ou sortant et le type d’appel passé par un utilisateur ou une conférence audio. Les types d’appels que vous pouvez voir sont les suivants :<br><br>**Types d’appels utilisateur teams**<ul><li>**dr_in** : l’utilisateur a reçu un appel RTC entrant</li><li>**dr_out** : l’utilisateur a placé un appel RTC sortant</li><li>**dr_out_user_conf** -l’utilisateur a ajouté un participant PSTN à l’appel</li><li>**user_out_transfer** : l’utilisateur a transféré l’appel vers un numéro PSTN.</li><li>**dr_out_user_forwarding** : l’utilisateur a renvoyé l’appel vers un numéro PSTN.</li><li>**dr_out_user_transfer** : l’utilisateur a transféré l’appel vers un numéro PSTN.</li><li>**dr_emergency_out** : l’utilisateur a émis un appel d’urgence</li></ul><br>**Types d’appels de robots teams**<ul><li>**dr_in_ucap** -un appel RTC entrant vers un bot de Microsoft Teams, tel que le standard automatique ou la file d’attente d’appels</li><li>**dr_out_ucap** -un appel RTC sortant d’un bot de Microsoft Teams, tel que le standard automatique ou la file d’attente d’appels</li></ul><br><li>**Appelé à** correspond au numéro de l’utilisateur qui a reçu l’appel.</li><li>**Heure de début (UTC)** est l’heure à laquelle le proxy SIP a reçu la réponse finale (message SIP "200 OK") de la SBC sur un appel sortant (Team/bot à un utilisateur RTC), ou après l’envoi de l’invitation au tronçon suivant du serveur principal Teams (utilisateur RTC à une équipe/bot). </li><li>**Temps d’invitation (UTC)** est l’heure à laquelle l’invitation initiale a été envoyée lors d’un appel sortant d’un utilisateur ou d’un appel de robots d’équipe à l’SBC, ou reçu lors d’un appel entrant à un appel d’équipe ou de robot par le composant proxy SIP du routage direct à partir de l’SBC.</li><li>**Temps d’échec (UTC)** est l’heure à laquelle l’appel a échoué. Pour les appels en échec uniquement. Le code SIP final, le sous-code final de Microsoft et la phrase SIP finale fournissent les raisons pour lesquelles l’appel a échoué et peut vous aider à résoudre les problèmes. </li><li>**Heure de fin (UTC)** est l’heure de fin de l’appel (pour les appels réussis uniquement).</li><li>**Durée** indique le temps de connexion de l'appel.</li><li>**Type de numéro** est le type de numéro de téléphone de l’utilisateur, par exemple un service de numéro gratuit. </li><li>**Contournement de média** indique si le Trunk a été activé pour la dérivation multimédia. </li> <li>Le **FQDN SBC** est le nom de domaine complet (FQDN) du contrôleur de bordure de session (SBC). </li><li>La **région Azure pour le média** est le centre de données utilisé comme chemin multimédia dans un appel sans contournement. </li><li>La **région Azure pour la signalisation** est le centre de données utilisé pour le signalement pour les appels de contournement et de non-contournement. </li><li>**Event type** est le type d’événement de l’appel. Vous verrez réussite pour les appels réussis et tentez d’essayer les appels en échec. </li><li>Le **code SIP final** correspond au code avec lequel l’appel a été interrompu.</li><li>Le sous- **code final de Microsoft** est un code qui indique des actions spécifiques qui se sont produites.</li><li>**Dernière phrase SIP** correspond à la description du code SIP et du sous-code Microsoft.</li><li>**ID de corrélation** est un identificateur unique de l’appel que vous pouvez utiliser lorsque vous appelez le support Microsoft.</li><li>L' **ID de corrélation partagé** est uniquement visible dans le fichier CSV téléchargeable et n’existe pas dans le portail. L’ID de corrélation partagée existe au moins deux appels liés. Veuillez consulter la description détaillée ci-dessous.</li></ul> Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau.|
|**5**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
|**6**   |Pour afficher le rapport en mode plein écran, sélectionnez **plein écran** . |
|**7**   |Sélectionnez **Exporter vers Excel** pour télécharger les données dans un fichier séparé par des virgules (CSV) pour une analyse hors connexion ou pour l’utiliser comme entrée pour votre système de facturation. |

**Considérations relatives aux champs appelant et appelé**

En fonction du sens de l’appel, le nom de l’appelant ou du visiteur peut contenir des numéros non-E164.

Ces champs peuvent provenir du ou des SBC du client. Il existe trois formats que l’SBC peut envoyer au routage direct : E. 164, des nombres non-E. 164 et des chaînes.

- E. 164 numéro de téléphone d’un utilisateur possédant un numéro E. 164 à un utilisateur qui possède également un numéro E. 164. 
- Appelez à partir d’un numéro non-E. 164. Un utilisateur d’un système PBX tiers connecté avec le routage direct effectue un appel à l’utilisateur d’équipes. Dans le cas présent, le numéro d’appelant peut être n’importe quel numéro non E. 164, par exemple + 1001. 
- Un expéditeur de courrier indésirable et ne présente pas de numéro, ce n’est qu’un nom (par exemple, « service de revenu interne »). Cette chaîne s’affichera dans les rapports.

**À propos de l’ID de corrélation partagée**

L’ID de corrélation partagée existe uniquement dans le fichier Excel exporté que vous téléchargez et indique que deux appels ou plus sont liés. Ce qui suit décrit les différents scénarios, et en présence d’ID de corrélation partagés.

1.  Utilisateur RTC 1 sur un point de terminaison PSTN appelé teams 1 sur le client Teams, type d’appel Dr_In, ID de corrélation 57f28917-42k5-4c0c-9433-79734873f2ac, aucun ID de corrélation partagée.
2.  Utilisateur teams 1 sur le client teams appelé utilisateur RTC 1 sur un point de terminaison PSTN, type d’appel Dr_Out 2c12b8ca-62eb-4c48-B68D-e451f518ff4, aucun ID de corrélation partagée.
3.  Utilisateur RTC 1 sur un point de terminaison PSTN appelé utilisateur d’équipe 2 sur le client Teams, type d’appel Dr_In f45e9a25-9f94-46e7-a457-84f5940efde9, ID de corrélation partagée f45e9a25-9f94-46e7-a457-84f5940efde9.
4.  Appel existant 3 avec ID de corrélation « f45e9a25-9f94-46e7-a457-84f5940efde9 ». Utilisateur RTC 1 en communication avec l’utilisateur teams 2. Utilisateur teams 2 a transféré (aveugle ou consultative) un appel vers teams ou un utilisateur RTC, type d’appel Dr_Out_User_Transfer 45a1da7c-9E97-481a-8a05-3fe19a9a77e0, ID de corrélation partagée f45e9a25-9f94-46e7-a457-84f5940efde9.

## <a name="related-topics"></a>Voir aussi

- [Analyses et rapports Teams](teams-reporting-reference.md)
