---
title: Liste des vues CDR
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
description: Les affichages offrent un moyen simple d’accéder aux informations sur les scénarios les plus courants utilisés pour renvoyer des données à partir de la base de données cdr. Il est recommandé d’utiliser des affichages pour créer des rapports personnalisés au lieu d’utiliser les tables de base de données d’cdr réelles ; Cela est dû au fait que les vues de base de données sont plus susceptibles de maintenir une compatibilité ascendante avec les futures sorties.
ms.openlocfilehash: 7154319dba584516dcff3c41d23e5af31bee4621
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746610"
---
# <a name="list-of-cdr-views"></a>Liste des vues CDR
 
Les affichages offrent un moyen simple d’accéder aux informations sur les scénarios les plus courants utilisés pour renvoyer des données à partir de la base de données cdr. Il est recommandé d’utiliser des affichages pour créer des rapports personnalisés au lieu d’utiliser les tables de base de données d’cdr réelles ; Cela est dû au fait que les vues de base de données sont plus susceptibles de maintenir une compatibilité ascendante avec les futures sorties.
  
|**Nom de la vue**|**Description**|
|:-----|:-----|
|[Affichage ClientVersions](clientversions-0.md) <br/> |Renvoie des informations sur le logiciel client/les appareils utilisés dans une session de communication.  <br/> |
|[Affichage ConferenceMessageCount](conferencemessagecount-0.md) <br/> |Renvoie des informations sur le nombre de messages envoyés par des utilisateurs pendant une conférence.  <br/> |
|[Affichage Des conférences](conferences-0.md) <br/> |Renvoie des informations sur la conférence, notamment l’heure de début, l’heure de fin et l’organisateur de la conférence.  <br/> |
|[Affichage ConferenceSessionDetails](conferencesessiondetails.md) <br/> |Renvoie des détails sur la session pour toutes les sessions de conférence, notamment les heures de début et de fin, les ID utilisateurs, les codes de réponse et les ID de diagnostic.  <br/> |
|[Affichage ConferenceUris](conferenceuris-0.md) <br/> |Renvoie des informations sur les URI de conférence utilisés pendant la conférence.  <br/> |
|[Affichage ErrorReport](errorreport-0.md) <br/> |Renvoie des informations sur les erreurs qui se sont produites pendant une session.  <br/> |
|[Vue FileTransfers](filetransfers.md) <br/> |Renvoie des informations sur les sessions de transfert de fichier, notamment le nom du fichier et si le transfert a été accepté, refusé ou annulé.  <br/> |
|[Affichage FocusJoinsAndLeaves](focusjoinsandleaves-0.md) <br/> |Renvoie des informations sur les activités de participation et de fin de participation à une conférence.  <br/> |
|[Affichage McuJoinsAndLeaves](mcujoinsandleaves-0.md) <br/> |Renvoie des informations combinées sur les activités de participation et de fin de participation à une conférence (chaque activité de participation à une conférence est associée à l’activité de fin de participation correspondante).  <br/> |
|[Affichage Mcus](mcus-0.md) <br/> |Renvoie des informations sur les serveurs de conférence.  <br/> |
|[Affichage multimédia](media-0.md) <br/> |Renvoie des informations sur les types de média utilisés dans les sessions de communication d’égal à égal.  <br/> |
|[Affichage ProgressReport](progressreport-0.md) <br/> |Renvoie des informations sur les sessions terminées.  <br/> |
|[Affichage d’inscription](registration-0.md) <br/> |Retourne des informations sur les inscriptions Skype Entreprise Server 2015.  <br/> |
|[Affichage SessionDetails](sessiondetails-0.md) <br/> |Renvoie des informations sur les sessions d’égal à égal, notamment les appels téléphoniques VoIP-VoIP, les sessions de messagerie instantanée à deux groupes ou d’autres sessions de communication d’égal à égal.  <br/> |
|[Affichage utilisateur](user.md) <br/> |Renvoie des informations sur les utilisateurs qui ont participé à des sessions de communication.  <br/> |
|[Affichage VoIPDetails](voipdetails.md) <br/> |Renvoie des informations sur les sessions d’égal à égal impliquant au moins un utilisateur de VoIP (Voix sur IP).  <br/> |
   

