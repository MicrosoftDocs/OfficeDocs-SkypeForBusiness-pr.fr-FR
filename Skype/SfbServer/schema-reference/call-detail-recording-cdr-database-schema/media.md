---
title: Table Media
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: Chaque enregistrement représente un type de média utilisé au cours d’une session d’égal à égal. Une session est représentée par plusieurs enregistrements dans la table, si plusieurs types de médias sont utilisés.
ms.openlocfilehash: a32a61d5ba7c3aa7d3a77008af373a5ea45daeda
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756467"
---
# <a name="media-table"></a>Table Media
 
Chaque enregistrement représente un type de média utilisé au cours d’une session d’égal à égal. Une session est représentée par plusieurs enregistrements dans la table, si plusieurs types de médias sont utilisés.
  
> [!NOTE]
> La table Media ne doit pas être utilisée pour calculer la durée du média lors d’une session. Cette table contient les détails de signalisation de l’échange multimédia lors d’une session. L’échange multimédia est effectué par la requête INVITE et StartTime indique l’heure à laquelle la requête INVITE a été envoyée. L’heure d’invitation ne signifie pas nécessairement l’heure de début du média, car le média démarre seulement lorsque le destinataire de la session accepte la session. EndTime signifie généralement l’heure de fin de cette session. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaire, étrangère  <br/> |Heure de la demande de session. Utilisée conjointement avec **SessionIdSeq** pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro d’ID pour identifier la session. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) <br/> |
|**MediaId** <br/> |tinyint  <br/> |Primaire, étrangère  <br/> |Numéro unique d’identification de ce type de média. Pour plus [d’informations, voir le tableau MediaList.](medialist.md) <br/> |
|**StartTime** <br/> |DateHeure  <br/> |Primaire  <br/> |Heure d’envoi de la demande multimédia, et non pas heure réelle du début du média. **StartTime** inclut l’heure de configuration de la session.<br/> |
|**EndTime** <br/> |DateHeure  <br/> ||Heure de fin de la session.  <br/> |
   

