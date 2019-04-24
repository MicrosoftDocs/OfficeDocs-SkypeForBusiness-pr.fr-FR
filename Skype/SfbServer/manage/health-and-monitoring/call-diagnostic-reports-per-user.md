---
title: Appeler des rapports de Diagnostic (par utilisateur) dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9da13470-001e-415f-b8c5-29b1f3b531ba
description: 'Résumé : Découvrez les utilisateur appel rapports de Diagnostic utilisés dans Skype pour Business Server.'
ms.openlocfilehash: 0c8e17151ab07814db2b07d1f0dda3ead3a509f9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200308"
---
# <a name="call-diagnostic-reports-per-user-in-skype-for-business-server"></a>Appeler des rapports de Diagnostic (par utilisateur) dans Skype pour Business Server
  
Les rapports de diagnostic des appels fournissent des informations par utilisateur concernant les sessions de conférence et P2P ayant échoué. À ce stade, il n'est qu’un rapport, le **Rapport d’activité de l’utilisateur**.

Le rapport d’activité de l’utilisateur fournit une liste détaillée des sessions P2P et des sessions de conférence exécutées par vos utilisateurs au cours d’une période donnée. Contrairement à la plupart des rapports de surveillance, le rapport d’activité de l’utilisateur lie chaque appel à des utilisateurs individuels. Par exemple, les sessions P2P spécifient les URI SIP de la personne à l’origine de l’appel (utilisateur d’origine) et celles de la personne qui a été appelée (utilisateur de destination). Si vous développez les informations sur une conférence, vous obtiendrez la liste de tous les participants à la conférence, ainsi que leur rôle à cette occasion.

Le rapport d’activité de l’utilisateur est parfois appelé « rapport de support technique ». En effet, ce rapport est souvent utilisé par les équipes de support technique pour récupérer les informations de session d’un utilisateur spécifique. Vous pouvez filtrer les appels à destination ou en provenance d’un utilisateur individuel en tapant simplement son URI SIP dans la zone Préfixe d’URI d’utilisateur.

Si vous faites cela, le rapport d’activité utilisateur retourne des informations pour tout utilisateur dont l’URI SIP commence par la chaîne spécifiée. Par exemple, si vous saisissez **ken** dans la zone URI, le rapport d’activité de l’utilisateur trouvera **Ken**.Myer@litwareinc.com. Cependant, Il trouvera aussi les utilisateurs suivants :

- **Ken** azi@litwareinc.com

- **Ken** burg@litwareinc.com

- **Ken**.Sanchez@litwareinc.com

- **Ken** nedy@litwareinc.com

Pour que les informations uniquement Ken Myer est retourné, tapez son URI complète (Ken.Myer@litwareinc.com) dans la zone de recherche ou au moins suffisamment type de Ken URI à lui distinguer d’autres utilisateurs de votre organisation. Par exemple :

Ken.my

## <a name="to-access-the-user-activity-report"></a>Pour accéder au rapport d’activité de l’utilisateur

Le rapport d’activité de l’utilisateur est accessible via la page d’accueil des rapports de surveillance. Vous pouvez également atteindre le User Activity Report en cliquant sur la mesure URI de l’utilisateur dans le [Rapport d’inventaire de téléphonie IP dans Skype pour Business Server](ip-phone-inventory-report.md). Si vous cliquez sur URI de la conférence (pour une conférence) dans le rapport d’activité de l’utilisateur, vous accéderez au rapport détaillé de conférence. De même, cliquez sur la mesure détails d’un appel d’égal à égal pour accéder au [rapport détaillé de Session d’égal à égal dans Skype pour Business Server](peer-to-peer-session-detail-report.md).

## <a name="making-the-best-use-of-the-user-activity-report"></a>Utilisation optimale du rapport d’activité de l’utilisateur

Même si le rapport d’activité de l’utilisateur contient des informations utiles, il peut parfois être difficile de les rechercher. Par exemple, toutes les activités utilisateur ayant lieu dans votre organisation pendant une période spécifiée sont incluses dans le rapport d’activité utilisateur ; que signifie que, caché, dans le rapport informations sur les utilisateurs réellement utilisés Skype pour Business Server d’une manière.

> [!NOTE]
> Techniquement, il est possible qu’une activité utilisateur peut accéder non enregistrée : while Skype pour Business Server cherche à conserver des informations sur tous les appels téléphoniques, il est possible qu’un appel aurait pu être sans les informations d’appel sont écrite dans le base de données. Skype pour Business Server est conçu pour donner un aspect extrêmement précis, mais pas nécessairement parfait à l’utilisation de Skype pour Business Server. (Le fait qu’il n’existe aucune garantie que 100 % de tous les appels sont enregistrés explique pourquoi Skype pour la surveillance Business Server ne doit pas être utilisé comme un système de facturation). Seconde, un rapport de surveillance peuvent uniquement affichage, au maximum 1 000 enregistrements. Ainsi, selon le volume d’activité de vos utilisateurs et la période considérée, votre requête risque de ne pas renvoyer toutes les données effectivement stockées dans la base de données. 

- Quels sont les utilisateurs qui ont utilisé le système au cours de cette période ?

- Parmi les différents utilisateurs, quels sont ceux qui se sont montrés les plus actifs au cours de cette période ?

- Les utilisateurs qui passent le plus grand nombre d’appels sont-ils aussi ceux qui participent le plus aux sessions de messagerie instantanée ?

Si vous avez besoin de répondre à ce type de question, vous pouvez exporter les données récupérées par les rapports de surveillance dans une feuille de calcul Excel. Vous pouvez alors vous servir de cette feuille de calcul et/ou d’un fichier de valeurs séparées par des virgules (CSV) pour analyser les données de façon plus poussée que dans le rapport d’activité de l’utilisateur. Par exemple, supposons que vous ayez exporté les données du rapport dans Excel, puis dans un fichier CSV. À ce stade, vous pouvez importer les données à partir de la. Fichier CSV de Windows PowerShell à l’aide d’une commande similaire à celle-ci :

```
$x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"
```

Une fois que les données ont été importées vous pouvez ensuite utiliser simples commandes Windows PowerShell pour aider à répondre à vos questions. Par exemple, cette commande renvoie une liste d’utilisateurs uniques qui ont fait office d’expéditeur (« From user ») dans au moins une session :

```
$x | Group-Object "From user" | Select Name | Sort-Object Name
```

En d’autres termes :

<pre>
Name
----
David.Ahs@litwareinc.com
Gilead.Amosnino@litwareinc.com
Henrik.Jensen@litwareinc.com
Ken.Myer@litwareinc.com
Pilar.Ackerman@litwareinc.com
</pre>

Cette commande dresse la liste des utilisateurs individuels (en fonction du nombre total de sessions auxquelles ils ont participé) :

```
$x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending
```

Les données renvoyées se présentent ainsi :

<pre>
Count    Name
-----    ----
  523    Ken.Myer@litwareinc.com
   63    David.Ahs@litwareinc.com
   29    Pilar.Ackerman@litwareinc.com
   17    Gilead.Amosnino@litwareinc.com
   10    Henrik.Jensen@litwareinc.com
</pre>

Cette commande limite les sessions recensées dans le rapport à celles qui incluaient la modalité audio :

```
$x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending
```

Si vous placez le curseur de la souris sur un ID de diagnostic figurant dans le rapport, une description de cet ID s’affiche dans une info-bulle.

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le rapport d’activité de l’utilisateur vous permet de filtrer les données renvoyées sur la base d’éléments tels que le type d’activité (à savoir, sessions P2P ou sessions de conférence) ou l’adresse SIP de l’utilisateur (vous permettant d’afficher les activités d’un utilisateur). Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les utilisations sont groupées par heure, jour, semaine ou mois.

Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport d’activité de l’utilisateur.

**Filtres du rapport d’activité de l’utilisateur**


| **Nom**   | **Description**  |
|:-----------|:--------|
| **De** <br/>             | Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 17/07/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 17/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 13/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/>                                                      |
| **À** <br/>               | Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 17/07/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 17/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 13/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/>                                                             |
| **Type d’activité** <br/>    | Type d’activité. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  Égal à égal <br/>  Conférence <br/>      |
| **Modalité** <br/>         | La modalité disponible varie selon le type d’activité sélectionné. Si le Type d’activité est égal à égal, vous pouvez sélectionner la messagerie instantanée ; Transfert de fichiers ; Application de partage ; Voix ; ou vidéo en tant que la modalité.  <br/> Si le type d’activité est Conférence, vous pouvez sélectionner messagerie instantanée, conférence web, partage d’application; conférence audio/vidéo ou téléconférence.  <br/>         |
| **Catégorie de session** <br/> | Indique si l’activité en question a réussi ou échoué. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  Opération réussie <br/>  Échec attendu <br/>  Échec inattendu <br/>  Un « échec attendu » est un échec prévisible. Par exemple, si un utilisateur a défini son statut sur Ne pas déranger, les appels passés à cet utilisateur échouent. Un « échec inattendu » est un échec qui se produit dans un système sain. Par exemple, un appel n’est pas censé s’interrompre lorsque l’appelant est mis en attente. Si cela se produit, l’incident est marqué comme un échec inattendu. <br/> |
| **Préfixe URI de l’utilisateur** <br/>  | Adresse SIP pour l’utilisateur. Pour afficher exclusivement les enregistrements de l’utilisateur Ken Myer, vous devez entrer l’adresse SIP de Ken Myer. Par exemple :  <br/> sip:kenmyer@litwareinc.com  <br/>

## <a name="metrics-for-peer-to-peer-sessions"></a>Mesures pour sessions P2P

Le tableau ci-dessous liste les informations fournies dans le rapport d’activité de l’utilisateur pour les sessions P2P (à savoir les sessions impliquant deux participants uniquement).

**Mesures pour sessions P2P**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Détails** <br/> |Non  <br/> |Lorsque vous cliquez sur cet élément, le rapport vous montre le Rapport détaillé de session P2P pour la session sélectionnée.  <br/> |
|**De l’utilisateur** <br/> |Oui  <br/> |Adresse SIP de l’utilisateur qui a initié la session P2P.  <br/> |
|**À l’utilisateur** <br/> |Oui  <br/> |Adresse SIP de l’utilisateur qui s’est joint à la session P2P.  <br/> |
|**Modalités** <br/> |Oui  <br/> |Type de communication utilisé dans la session. Par exemple, messagerie instantanée, audio ou transfert de fichier.  <br/> |
|**Heure d’invitation** <br/> |Oui  <br/> |Date et heure d’envoi de l’invitation initiale à se joindre à la session P2P.  <br/> |
|**Heure de réponse** <br/> |Oui  <br/> |Date et heure d’acceptation de la session par l’utilisateur « À ».  <br/> |
|**Heure de fin** <br/> |Oui  <br/> |Date et heure de fin de la session P2P.  <br/> |
|**ID de diagnostic** <br/> |Oui  <br/> |Identificateur unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui fournit souvent des informations utiles pour résoudre des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible que des sessions SIP n’incluent pas ces en-têtes) et les ID de diagnostic sont uniquement signalés pour les sessions qui ont rencontré des problèmes, quels qu’ils soient.  <br/> |

## <a name="metrics-for-conferencing-sessions"></a>Mesures pour les sessions de conférence

Le tableau ci-dessous liste les informations fournies dans le rapport d’activité de l’utilisateur pour les sessions P2P (à savoir les sessions impliquant deux participants uniquement).

**Mesures pour les sessions de conférence**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**URI de la conférence** <br/> |Oui  <br/> |Identifiant de conférence unique. Lorsque vous cliquez sur cet élément, le rapport vous montre le Rapport détaillé de conférence pour la session sélectionnée. Lorsque vous développez cet élément, le rapport vous montre les informations sur les participants à la conférence. Pour des informations détaillées, consultez la section « Mesures pour les participants de la conférence », dans la suite de cette rubrique.  <br/> |
|**Organisateur** <br/> |Oui  <br/> |Adresse SIP de l’utilisateur qui a organisé la conférence.  <br/> |
|**Pool** <br/> |Oui  <br/> |Nom du serveur Edge (le cas échéant) utilisé dans la conférence.  <br/> |
|**Heure de début** <br/> |Oui  <br/> |Date et heure de début de la conférence.  <br/> |
|**Heure de fin** <br/> |Oui  <br/> |Date et heure de fin de la conférence.  <br/> |

## <a name="metrics-for-conference-participants"></a>Mesures pour les participants de la conférence

Le tableau ci-dessous répertorie les informations fournies dans le Rapport d’activité de l’utilisateur sur chaque participant d’une conférence.

**Mesures pour les participants de la conférence**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Rôle** <br/> |Non  <br/> |Rôle de conférence (par exemple, Présentateur) pour l’utilisateur.  <br/> |
|**Participant** <br/> |Non  <br/> |Adresse SIP de l’utilisateur.  <br/> |
|**Connectivité** <br/> |Non  <br/> |Type de connexion réseau. Par exemple, « Depuis interne » pour une connexion interne ou « Depuis RTC » pour les utilisateurs d’appels entrants.  <br/> |
|**Heure d’arrivée** <br/> |Non  <br/> |Date et heure à laquelle l’utilisateur a rejoint la conférence.  <br/> |
|**Heure de départ** <br/> |Non  <br/> |Date et heure à laquelle l’utilisateur a quitté la conférence.  <br/> |
|**ID de diagnostic** <br/> |Non  <br/> |Identificateur unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui fournit souvent des informations utiles pour résoudre des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible que des sessions SIP n’incluent pas ces en-têtes) et les ID de diagnostic sont uniquement signalés pour les sessions qui ont rencontré des problèmes, quels qu’ils soient.  <br/> |

