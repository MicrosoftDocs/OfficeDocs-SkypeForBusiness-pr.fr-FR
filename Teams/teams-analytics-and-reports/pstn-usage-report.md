---
title: Rapport d’utilisation du RTC Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
description: Découvrez comment utiliser le rapport d’utilisation du RTC Teams dans le Centre d’administration Microsoft Teams pour obtenir une vue d’ensemble de l’utilisation des appels et de l’audioconférence dans votre organisation.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e06a2f5a70a50e1b73978a289a9a2680cd296fc0
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794542"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Rapport d’utilisation du RTC Microsoft Teams

Le rapport d’utilisation du RTC Teams (réseau téléphonique commuté public) dans le Centre d’administration Microsoft Teams vous donne une vue d’ensemble de l’activité d’appel et d’audioconférence dans votre organisation. Vous pouvez afficher l’activité d’appel détaillée pour les forfaits d’appels si vous utilisez Microsoft comme opérateur de téléphonie et pour le routage direct si vous utilisez votre propre opérateur de téléphonie.

L’onglet **Forfaits** d’appels affiche des informations, notamment le nombre de minutes passées par les utilisateurs dans les appels RTC entrants et sortants, ainsi que le coût de ces appels. L’onglet **Routage direct** affiche des informations, notamment l’adresse SIP et les heures de début et de fin des appels. Utilisez les informations contenues dans ce rapport pour obtenir des informations sur l’utilisation du RTC dans votre organisation et vous aider à examiner, planifier et prendre des décisions commerciales.

> [!NOTE]
> Si vous avez un plan d’appels Telstra ou Softbank, vous ne verrez aucun enregistrement détaillé des appels dans le rapport d’utilisation du RTC. Contactez Telstra ou Softbank pour vos besoins en matière de création de rapports. 

## <a name="view-the-pstn-usage-report"></a>Afficher le rapport d’utilisation PSTN

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Analyse & rapports** > **d’utilisation**. Sous l’onglet **Afficher les rapports** , sous **Rapport**, sélectionnez rapport **d’utilisation RTC**.
2. Sous **Plage de dates**, sélectionnez une plage prédéfinie de 7 ou 28 jours, ou définissez une plage personnalisée, puis sélectionnez **Exécuter le rapport**.

## <a name="interpret-the-report"></a>Interpréter le rapport

### <a name="calling-plans"></a>Forfaits d’appel

   ![Capture d’écran du rapport d’utilisation PSTN des forfaits d’appels dans le Centre d’administration](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png)![Capture d’écran du rapport d’utilisation rtc dans le Centre d’administration Microsoft Teams avec des légendes numérotées](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png#lightbox)

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport peut être consulté pour les tendances des 7 derniers jours, 28 jours ou une plage de dates personnalisée que vous avez définie. |
|**2**   |Chaque rapport a une date de génération. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l'heure de l'activité. |
|**3**   |L’axe X est la plage de dates sélectionnée pour le rapport spécifique. L’axe Y est le nombre total d’appels sur la période sélectionnée. <br>Pointez sur le point à une date donnée pour voir le nombre total d’appels effectués à cette date.  |
|**4**   |Le tableau vous donne une répartition de l’utilisation PSTN par appel. <ul><li>**L’horodatage (UTC)** correspond à l’heure de début de l’appel.</li><li>**Le nom d’affichage** est le nom complet de l’utilisateur. Vous pouvez cliquer sur le nom d’affichage pour accéder à la page de paramètres de l’utilisateur dans le Centre d’administration Microsoft Teams.</li><li>**Le nom d’utilisateur** est le nom de connexion de l’utilisateur.</li><li>**Le numéro de téléphone** est le numéro qui a reçu l’appel pour les appels entrants ou le numéro composé pour les appels sortants.</li><li>**Le type d’appel** est de savoir si l’appel était un appel sortant ou entrant RTC et le type d’appel tel qu’un appel passé par un utilisateur ou une conférence audio. Les types d’appels que vous pouvez voir sont les suivants :<br><br>**Types d’appels d’utilisateur Teams**<ul><li>**user_in** : l’utilisateur a reçu un appel RTC entrant</li><li>**user_out** : l’utilisateur a passé un appel RTC sortant</li><li>**user_out_conf** : l’utilisateur a ajouté au moins deux participants RTC à l’appel, par exemple une téléconférence triple</li><li>**user_out_transfer** : l’utilisateur a transféré l’appel à un numéro RTC</li><li>**user_out_forwarding** : l’utilisateur a transféré l’appel à un numéro RTC</li><li>**conf_in** : un appel entrant au pont d’audioconférence</li><li>**conf_out** : un appel sortant du pont d’audioconférence généralement pour ajouter un numéro RTC à la conférence</li><li>**unassigned_in** : un appel RTC entrant via le plan d’appel à un numéro non attribué</li></ul><br>**Types d’appels des bots Teams**<ul><li>**ucap_in** : un appel RTC entrant au bot Teams, tel qu’un standard automatique ou une file d’attente d’appels</li><li>**ucap_out** : un appel RTC sortant à partir d’un bot Teams tel qu’un standard automatique ou une file d’attente d’appels</li></ul><br><li>**Appelé est** le numéro composé.</li><li>**Vers le pays ou la région** est le pays ou la région composé.</li><li>**Appelé à partir du** numéro qui a placé l’appel.</li><li>**À partir du pays ou de la région** est le pays ou la région d’où l’appel a été passé.</li><li>**Les frais** correspondent au montant ou au coût de l’appel facturé à votre compte. </li><li>**Currency** est le type de devise utilisé pour calculer le coût de l’appel. </li><li>**Durée** indique le temps de connexion de l'appel.</li><li>**Domestic/International** vous indique si l’appel était national (au sein d’un pays ou d’une région) ou international (en dehors d’un pays ou d’une région) en fonction de l’emplacement de l’utilisateur.</li><li>**L’ID** d’appel est l’ID d’appel d’un appel. Il s’agit d’un identificateur de l’appel que vous pouvez utiliser lors de l’appel Support Microsoft.</li><li>**Le type de** numéro est le type de numéro de téléphone de l’utilisateur, tel qu’un service de numéro gratuit. </li><li>**Le pays ou la région** est l’emplacement d’utilisation. </li> <li>**L’ID de conférence** est l’ID de conférence de la conférence audio. </li><li>**La fonctionnalité** est la licence utilisée pour l’appel. Les types de licences que vous pouvez voir sont les suivants :<ul><li>**MCOEV ou MCOEV_VIRTUALUSER ou MCOEV_VIRTUALUSER_GOV** - Applications vocales telles que le standard automatique ou les files d’attente d’appels</li><li>**FREECALL** - En cas de problème technique qui nous empêche de tarification d’un appel, l’appel est fourni gratuitement et apparaîtra avec cette fonctionnalité</li><li>**MCOPSTN1** - Forfait d’appels nationaux (3000 min US / 1200 min plans de l’UE)</li><li>**MCOPSTN2** - Plan d’appels internationaux</li><li>**MCOPSTN5** - Forfait d’appels nationaux (forfait d’appels de 120 minutes)</li><li>**MCOPSTN6** - Forfait d’appels nationaux (forfait d’appels de 240 minutes)</li><li>**MCOPSTN8** - Forfait d’appels nationaux 120 min par utilisateur (non regroupé entre les utilisateurs comme les autres forfaits d’appels)</li><li>**MCOPSTN9** - Plan d’appels internationaux</li><li>**MCOPSTNCAP** - Common Area Phone</li><li>**MCOPSTNPP** - Crédits de communication</li><li>**MCOMEETADD** - Audioconférence</li><li>**MCOMEETADD_DIALOUT_US** - Plan d’appel d’audioconférence des États-Unis et du Canada</li><li>**MCOMEETADD_CN_GLOBAL** - Audioconférence pour les utilisateurs non chinois</li><li>**MCOMEETADD_TATA** - Connexions Tata Communications</li><li>**MCOMEETACPEA** - Audioconférence avec paiement à la minute </li><li>**MCOMEETACPEA_GOV** - Audioconférence payante par minute pour le gouvernement</li></ul></li></ul> Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau.|
|**5**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
|**6**   |Sélectionnez **Filtrer** pour filtrer le rapport par nom d’utilisateur ou type d’appel. |
|**7**   |Sélectionnez **Plein écran** pour afficher le rapport en mode plein écran. |
|**8**   |Vous pouvez exporter le rapport vers un fichier CSV pour une analyse hors connexion. Cliquez sur **Exporter vers Excel**, puis sous l’onglet **Téléchargements** , cliquez sur **Télécharger** pour télécharger le rapport lorsqu’il est prêt.|

### <a name="direct-routing"></a>Routage direct

   ![Capture d’écran du rapport d’utilisation rtc du routage direct dans le Centre d’administration](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png)![Capture d’écran du rapport d’utilisation rtc du routage direct dans le Centre d’administration Microsoft Teams avec des légendes numérotées](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png#lightbox)

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport peut être consulté pour les tendances des 7 ou 28 derniers jours. |
|**2**   |Chaque rapport a une date de génération. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l'heure de l'activité. |
|**3**   |L’axe X est la plage de dates sélectionnée pour le rapport spécifique. L’axe Y est le nombre total d’appels sur la période sélectionnée.<br>Pointez sur le point à une date donnée pour voir le nombre total d’appels effectués à cette date.  |
|**4**   |Le tableau vous donne une répartition de l’utilisation PSTN par appel. <ul><li>**L’horodatage (UTC)** correspond à l’heure de début de l’appel.</li><li>**Le nom d’affichage** est le nom complet de l’utilisateur. Vous pouvez cliquer sur le nom d’affichage pour accéder à la page des paramètres de l’utilisateur dans le Centre d’administration Microsoft Teams. Le nom peut également être le nom d’un bot, par exemple la file d’attente des appels ou le standard automatique cloud. </li><li>**L’adresse SIP** est l’adresse SIP de l’utilisateur ou d’un bot qui a reçu ou effectué l’appel.</li><li>**Le numéro d’appelant** est le numéro de l’utilisateur ou du bot qui a effectué l’appel. </li><li>**Le numéro** d’appelé est le numéro de l’utilisateur ou du bot qui a reçu l’appel. Lors d’un appel entrant à un utilisateur Teams, il s’agit de l’utilisateur Teams. Lors d’un appel sortant d’un utilisateur Teams, il s’agit de l’utilisateur RTC. </li><li>**Le type d’appel** est de savoir si l’appel était un appel sortant ou entrant RTC et le type d’appel tel qu’un appel passé par un utilisateur ou une conférence audio. Les types d’appels que vous pouvez voir sont les suivants :<br><br>**Types d’appels d’utilisateur Teams**<ul><li>**dr_in** : l’utilisateur a reçu un appel RTC entrant</li><li>**dr_out** : l’utilisateur a passé un appel RTC sortant</li><li>**dr_out_user_conf** : l’utilisateur a ajouté un participant RTC à l’appel</li><li>**user_out_transfer** : l’utilisateur a transféré l’appel à un numéro RTC</li><li>**dr_out_user_forwarding** : l’utilisateur a transféré l’appel à un numéro RTC</li><li>**dr_out_user_transfer** : l’utilisateur a transféré l’appel à un numéro RTC</li><li>**dr_emergency_out** : l’utilisateur a effectué un appel d’urgence</li><li>**dr_unassigned_in** : un appel RTC entrant via le routage direct vers un numéro non attribué</li></ul><br>**Types d’appels des bots Teams**<ul><li>**dr_in_bot** : un appel RTC entrant à un bot Teams, tel qu’un standard automatique ou une file d’attente d’appels</li><li>**dr_out_bot** : un appel RTC sortant à partir d’un bot Teams tel qu’un standard automatique ou une file d’attente d’appels</li></ul><br><li>**Appelé est** le numéro de l’utilisateur qui a reçu l’appel.</li><li>**L’heure de début (UTC)** correspond à l’heure à laquelle le proxy SIP a reçu la réponse finale (message SIP « 200 OK ») du SBC lors d’un appel sortant (Teams/Bot à un utilisateur RTC), ou après que le proxy SIP a envoyé l’invitation au tronçon suivant dans le backend Teams lors d’un appel entrant (utilisateur RTC à teams/bot). </li><li>**L’heure d’invitation (UTC)** est l’heure à laquelle l’invitation initiale a été envoyée lors d’un appel sortant à partir d’un appel d’utilisateur ou de bot Teams au SBC, ou reçue lors d’un appel entrant à un appel Teams ou bot par le composant proxy SIP du routage direct à partir du SBC.</li><li>**Le temps d’échec (UTC)** correspond à l’heure à laquelle l’appel a échoué. Pour les appels ayant échoué uniquement. Le code SIP final, le sous-code Microsoft final et l’expression SIP finale fournissent les raisons pour lesquelles l’appel a échoué et peuvent vous aider à résoudre les problèmes. </li><li>**L’heure de fin (UTC)** est l’heure de fin de l’appel (pour les appels réussis uniquement).</li><li>**La durée** correspond à la durée pendant laquelle l’appel a été connecté, de l’invitation à la fin ou à l’échec de l’appel. Pour le transfert d’appel, la durée inclut la sonnerie dans la file d’attente d’appels.</li><li>**Le type de** numéro est le type de numéro de téléphone de l’utilisateur, tel qu’un service de numéro gratuit. </li><li>**La déviation** du trafic multimédia indique si la jonction a été activée pour le contournement du média. </li> <li>**SBC FQDN** est le nom de domaine complet (FQDN) du contrôleur de frontière de session (SBC). </li><li>**La région Azure pour les médias** est le centre de données qui a été utilisé comme chemin d’accès multimédia dans un appel sans contournement. </li><li>**La région Azure pour la signalisation** est le centre de données qui a été utilisé pour la signalisation pour les appels de contournement et de non-contournement. </li><li>**Le type d’événement** est le type d’événement de l’appel. Vous verrez la réussite des appels réussis et la tentative d’échec des appels. </li><li>**Le code SIP final** est le code avec lequel l’appel s’est terminé.</li><li>**Le sous-code Microsoft final** est un code qui indique des actions spécifiques qui se sont produites.</li><li>**L’expression SIP finale** est la description du code SIP et du sous-code Microsoft.</li><li>**L’ID de corrélation** est un identificateur unique pour l’appel que vous pouvez utiliser lors de l’appel Support Microsoft.</li><li>**L’ID de corrélation partagée** est visible uniquement dans le fichier CSV téléchargeable et n’existe pas dans le portail. L’ID de corrélation partagé existe dans au moins deux appels associés. Consultez la description détaillée ci-dessous.</li></ul> Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau.|
|**5**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
|**6**   |Sélectionnez **Plein écran** pour afficher le rapport en mode plein écran. |
|**7**   |Sélectionnez **Exporter vers Excel** pour télécharger les données dans un fichier séparé par des virgules (CSV) à des fins d’analyse hors connexion ou pour les utiliser comme entrée pour votre système de facturation. |

#### <a name="callercallee-fields-considerations"></a>Considérations relatives aux champs Appelant/Appelé

Selon la direction de l’appel, les noms d’appelant ou d’appelé peuvent contenir des numéros non E164.

Ces champs peuvent provenir du(s) SBC(s) client(s). Le SBC peut envoyer trois formats au routage direct : les nombres E.164, les nombres non E.164 et les chaînes.

- Numéro de téléphone E.164 d’un utilisateur disposant d’un numéro E.164 à un utilisateur qui a également un numéro E.164. 
- Appel à partir d’un numéro autre que E.164. Un utilisateur d’un PBX tiers interconnecté avec le routage direct effectue un appel à un utilisateur Teams. Dans ce cas, le numéro d’appelant peut être n’importe quel numéro autre que E.164, par exemple +1001. 
- Un spammeur appelle et ne présente pas de nombre, mais seulement un nom, par exemple « Internal Revenue Service ». Cette chaîne s’affiche dans les rapports.

#### <a name="phone-number-obfuscation"></a>Obfuscation de numéro de téléphone
Les exigences de confidentialité par pays incluent l’obfuscation des numéros de téléphone externes (non détenus par le client). Les trois ou quatre derniers chiffres du numéro de téléphone sont remplacés par des astérisques (+123 456789***). 

Pour les appels entrants, le numéro de l’appelant est masqué. Pour les appels sortants, le numéro d’appelé est masqué. Cela s’applique aux rapports rtc et de routage direct dans le Centre de Administration client, à l’exportation des données et aux journaux d’appels disponibles via Microsoft Graph.

L’obfuscation est basée sur l’emplacement de l’organisation (pays). Les numéros de téléphone complets sont affichés pour les pays qui ne sont pas répertoriés dans le tableau suivant :

| Pays | Nombre de chiffres d’obfuscation |
| :-: | :- |
|BE – Belgique | 3 |
|CH – Suisse | 4 |
|DE - Allemagne | 3 |
|DK – Danemark | 3 |
|ES – Espagne | 3 |
|FI – Finlande | 3 |
|FR – France | 4 |
|It – Italie | 3 |
|NL - Pays-Bas | 3 |
|NO - Norvège | 3 |
|SE - Suède | 3 |

#### <a name="about-shared-correlation-id"></a>À propos de l’ID de corrélation partagé

L’ID de corrélation partagée existe uniquement dans le fichier Excel exporté que vous téléchargez et indique que deux appels ou plus sont liés. Ce qui suit explique les différents scénarios et quand l’ID de corrélation partagée est présent.

1.    Utilisateur RTC 1 sur un point de terminaison RTC appelé Teams User 1 sur le client Teams, type d’appel Dr_In, ID de corrélation 57f28917-42k5-4c0c-9433-79734873f2ac, aucun ID de corrélation partagé.
2.    Utilisateur Teams 1 sur le client Teams appelé Utilisateur RTC 1 sur un point de terminaison RTC, type d’appel Dr_Out 2c12b8ca-62eb-4c48-b68d-e451f518ff4, aucun ID de corrélation partagé.
3.    Utilisateur RTC 1 sur un point de terminaison RTC appelé utilisateur Teams 2 sur le client Teams, type d’appel Dr_In f45e9a25-9f94-46e7-a457-84f5940efde9, ID de corrélation partagé f45e9a25-9f94-46e7-a457-84f5940efde9.
4.    Appel existant 3 avec l’ID de corrélation « f45e9a25-9f94-46e7-a457-84f5940efde9 ». Utilisateur RTC 1 dans un appel avec l’utilisateur Teams 2. L’utilisateur Teams 2 a transféré (aveugle ou consultatif) un appel à Teams ou à un utilisateur RTC, type d’appel Dr_Out_User_Transfer 45a1da7c-9e97-481a-8a05-3fe19a9a77e0, ID de corrélation partagé f45e9a25-9f94-46e7-a457-84f5940efde9.

## <a name="exporting-the-reports"></a>Exportation des rapports
Cliquez sur **Exporter vers Excel**, puis sous l’onglet **Téléchargements** , cliquez sur **Télécharger** pour télécharger le rapport lorsqu’il est prêt. Le processus d’exportation peut prendre de quelques secondes à plusieurs minutes, en fonction de la quantité de données.

Cela exportera les données de tous les utilisateurs et vous permettra de trier et de filtrer plus simplement pour une analyse ultérieure. Les fichiers exportés contiennent des champs supplémentaires qui ne sont pas disponibles dans le rapport en ligne. Ceux-ci peuvent être utilisés pour la résolution des problèmes et les flux de travail automatisés.

 Vous recevrez un fichier zip nommé « **Calls.Export.`[identifier]`.zip**« , l’identificateur étant un ID unique pour l’exportation qui peut être utilisé pour la résolution des problèmes.

Si vous avez à la fois des forfaits d’appels et un routage direct, le fichier exporté peut contenir des données pour les deux produits. Le fichier de rapport d’utilisation RTC aura le nom de fichier « **PSTN.calls.`[UTC date]`.csv**» et le routage direct « **DirectRouting.calls.`[UTC date]`.csv**« .

 Outre les fichiers PSTN et Direct Routing, l’archive contient le fichier « **parameters.json** », avec l’intervalle de temps d’exportation et les fonctionnalités sélectionnés.

Les fichiers exportés sont au format CSV (Virgul Separated Values), conforme à [la norme RFC 4180](https://tools.ietf.org/html/rfc4180) . Les fichiers peuvent être ouverts dans Excel ou tout autre éditeur conforme aux normes sans nécessiter de transformations.

La première ligne du fichier CSV contient des noms de colonnes. Toutes les dates sont au format UTC et [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) .

### <a name="exported-pstn-usage-report"></a>Rapport d’utilisation PSTN exporté

 Vous pouvez exporter des données jusqu’à un an à partir de la date actuelle, sauf si des réglementations spécifiques à un pays interdisent la conservation des données pendant 12 mois.

> [!div class="has-no-wrap"]  
> | # | Nom | [Type de données (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | Description |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | Identificateur d’appel unique |
> | 1 | ID d’appel | `nvarchar(64)` | Identificateur d’appel. Il n’est pas garanti qu’il soit unique |
> | 2 | ID de conférence | `nvarchar(64)` | ID de la conférence audio |
> | 3 | Emplacement de l’utilisateur | `nvarchar(2)` | Code de pays de l’utilisateur, [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | Appel de l’ID de l’utilisateur dans Azure Active Directory.<br/> Ces informations utilisateur et d’autres seront null/vides pour les types d’appels de bot (ucap_in, ucap_out) |
> | 5 | UPN | `nvarchar(128)` | UserPrincipalName (nom de connexion) dans Azure Active Directory.<br/>Il s’agit généralement de l’adresse SIP de l’utilisateur et peut être identique à l’adresse de messagerie de l’utilisateur. |
> | 6 | Nom d’affichage de l’utilisateur | `nvarchar(128)` | Nom d’affichage de l’utilisateur |
> | 7 | ID de l’appelant | `nvarchar(128)` | Numéro qui a reçu l’appel pour les appels entrants ou numéro composé pour les appels sortants. [Format E.164](https://en.wikipedia.org/wiki/E.164) |
> | 8 | Type d'appel | `nvarchar(32)` | Indique si l’appel était un appel sortant ou entrant RTC et le type d’appel tel qu’un appel passé par un utilisateur ou une conférence audio |
> | 9 | Type de nombre | `nvarchar(16)` | Type de numéro de téléphone de l’utilisateur, tel qu’un service de numéro gratuit |
> | 10 | National/International | `nvarchar(16)` | Si l’appel était national (au sein d’un pays ou d’une région) ou international (en dehors d’un pays ou d’une région) en fonction de l’emplacement de l’utilisateur |
> | 11 | Destination numérotée | `nvarchar(64)` | Pays ou région composé |
> | 12 | Numéro de destination | `nvarchar(32)` | Numéro composé au format [E.164](https://en.wikipedia.org/wiki/E.164) |
> | 13 | Heure de début | `datetimeoffset` | Heure de début de l’appel |
> | 14 | Heure de fin | `datetimeoffset` | Heure de fin de l’appel |
> | 15 | Durée des secondes | `int` | Durée de connexion de l’appel |
> | 16 | Frais de connexion | `numeric(16, 2)` | Prix des frais de connexion |
> | 17 | Frais | `numeric(16, 2)` | Montant ou coût de l’appel facturé à votre compte |
> | 18 | Devise | `nvarchar(3)` | Type de devise utilisé pour calculer le coût de l’appel ([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)) |
> | 19 | Fonctionnalité | `nvarchar(32)` | Licence utilisée pour l’appel |

### <a name="exported-direct-routing-usage-report"></a>Rapport d’utilisation du routage direct exporté

Vous pouvez exporter des données jusqu’à cinq mois (150 jours) à partir de la date actuelle, sauf si les réglementations spécifiques au pays interdisent la conservation des données pour cette période.

> [!div class="has-no-wrap"]  
> | # | Nom | [Type de données (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | Description |
> | :-: | :-: | :-: |:------------------- |
> | 0 | Correlationid | `uniqueidentifier` | Identificateur d’appel. Plusieurs jambes du même appel peuvent partager le même CorrelationId |
> | 1 | AAD ObjectId | `uniqueidentifier` | Appel de l’ID de l’utilisateur dans Azure Active Directory.<br/> Ces informations utilisateur et d’autres peuvent être null/vides pour les types d’appels de bot |
> | 2 | UPN | `nvarchar(128)` | UserPrincipalName (nom de connexion, Azure Active Directory) de l’utilisateur ou du bot qui a effectué ou reçu l’appel.<br/>Il s’agit généralement de l’adresse SIP de l’utilisateur et peut être identique à l’adresse de messagerie de l’utilisateur. |
> | 3 | Nom d’affichage | `nvarchar(128)` | Nom d’un utilisateur ou d’un bot appelant (par exemple, File d’attente d’appels ou Standard automatique) défini dans Centre d'administration Microsoft 365 |
> | 4 | Pays de l’utilisateur | `nvarchar(2)` | Code de pays de l’utilisateur, [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 5 | Heure d’invitation | `datetimeoffset` | Lorsque l’invite initiale envoie un appel sortant à partir d’un utilisateur ou d’un bot Teams vers le SBC, ou lorsqu’elle est reçue en entrant vers Teams ou un appel de bot par le composant proxy SIP du routage direct à partir du SBC |
> | 6 | Heure de début | `datetimeoffset` | Heure à laquelle le proxy SIP a reçu la réponse finale (message SIP « 200 OK ») du serveur SBC en sortie (Teams/Bot vers un utilisateur RTC), ou après que le proxy SIP a envoyé l’invitation au tronçon suivant dans le backend Teams lors d’un appel entrant (utilisateur RTC à teams/bot).<br/>Pour les appels ayant échoué et sans réponse, cela peut être égal au temps d’invitation ou d’échec |
> | 7 | Temps d’échec | `datetimeoffset` | Existe uniquement pour les appels ayant échoué (non entièrement établis) |
> | 8 | Heure de fin | `datetimeoffset` | Il n’existe que pour les appels réussis (entièrement établis). Heure à laquelle l’appel s’est terminé |
> | 9 | Durée (secondes) | `int` | Durée de l’appel, de l’invitation à la fin ou à l’échec de l’appel. Pour le transfert d’appel, la durée inclut la sonnerie dans la file d’attente d’appels. |
> | 10 | Opération réussie | `nvarchar(3)` | Oui/Non. Réussite ou tentative |
> | 11 | Numéro de l’appelant | `nvarchar(32)` | Numéro de l’utilisateur ou du bot qui a effectué l’appel. Lors de l’appel d’un utilisateur d’équipe entrant, il s’agit d’un utilisateur RTC, à partir de l’appel d’un utilisateur Teams, il s’agit du numéro d’utilisateur Teams. |
> | 12 | Numéro de l’appelé | `nvarchar(32)` | Numéro de l’utilisateur ou du bot qui a reçu l’appel. Lors de l’appel d’un utilisateur d’équipe entrant, il s’agit de l’utilisateur Teams, à partir de l’appel de l’utilisateur Teams, il s’agit de l’utilisateur RTC. |
> | 13 | Type d’appel | `nvarchar(32)` | Type d’appel et direction |
> | 14 | Région Azure pour les médias | `nvarchar(8)` | Centre de données utilisé pour le chemin du média dans l’appel sans contournement |
> | 15 | Région Azure pour la signalisation | `nvarchar(8)` | Centre de données utilisé pour la signalisation pour les appels de contournement et de non-contournement |
> | 16 | Code SIP final | `int` | Code avec lequel l’appel s’est terminé, [RFC 3261](https://tools.ietf.org/html/rfc3261) |
> | 17 | Sous-code Microsoft final | `int` | En plus des codes SIP, Microsoft possède ses propres sous-codes qui indiquent le problème spécifique |
> | 18 | Phrase SIP finale | `nvarchar(256)` | Description du code SIP et du sous-code Microsoft |
> | 19 | Nom de domaine complet SBC | `nvarchar(64)` | Nom de domaine complet du contrôleur de bordure de session |
> | 20 | Contournement de média | `nvarchar(3)` | Oui/Non. Indique si la jonction a été activée pour le contournement du média ou non |
> | 21 | ID de corrélation partagé | `uniqueidentifier` | Indique que deux appels ou plus sont liés |


## <a name="related-topics"></a>Sujets associés

- [Analyses et rapports Teams](teams-reporting-reference.md)
- [Rapport d’appel RTC dans Microsoft Graph](/graph/api/callrecords-callrecord-getpstncalls?view=graph-rest-1.0&tabs=http)
- [Rapport de routage direct dans Microsoft Graph](/graph/api/callrecords-callrecord-getdirectroutingcalls?view=graph-rest-1.0&tabs=http)
