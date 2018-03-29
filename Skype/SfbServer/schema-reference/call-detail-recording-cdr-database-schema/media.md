---
title: Table Media
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: Chaque enregistrement représente un type de support utilisé dans une session peer-to-peer. Une session est représentée par plusieurs enregistrements de la table, si plus d’un type de média est utilisé.
ms.openlocfilehash: 8833e7272c82dcbb7eef0da89d915680198589b5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="media-table"></a>Table Media
 
Chaque enregistrement représente un type de support utilisé dans une session peer-to-peer. Une session est représentée par plusieurs enregistrements de la table, si plus d’un type de média est utilisé.
  
> [!NOTE]
> La table Media ne doit pas servir pour calculer la durée d’une session de média. Cette table contient les détails de signalisation de l’échange de médias dans une session. Échange de médias est effectué par la demande d’invitation et StartTime indique l’heure à laquelle l’invitation a été envoyée. L’heure de l’invitation ne signifie pas nécessairement que le support de démarrage, car le média ne démarre qu’après que le sessionee accepte la session. L’heure de fin signifie généralement que l’heure de fin de cette session. 
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaires et étrangères  <br/> |Heure de la demande de la session. Utilisé en association avec **SessionIdSeq** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaires et étrangères  <br/> |Numéro d’ID pour identifier la session. Utilisé en association avec **SessionIdTime** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**MediaId** <br/> |tinyint  <br/> |Primaires et étrangères  <br/> |Numéro unique identifiant ce type de média. Consultez le [tableau de MediaList](medialist.md) pour plus d’informations. <br/> |
|**Heure de début** <br/> |DateHeure  <br/> |Principal  <br/> |Il s’agit de l’heure à laquelle une demande de support a été envoyée, pas le support réel de démarrage. **StartTime** comprend le temps du programme d’installation de session. <br/> |
|**Heure de fin** <br/> |DateHeure  <br/> ||Il s’agit de l’heure de fin de la session.  <br/> |
   

