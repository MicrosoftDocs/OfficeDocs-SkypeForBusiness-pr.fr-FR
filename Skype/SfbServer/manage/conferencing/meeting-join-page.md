---
title: Configurer la réunion page jointure dans Skype pour Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Résumé : Apprenez à configurer la réunion page jointure dans Skype pour Business Server 2015.'
ms.openlocfilehash: c0b3ed39fc2f7a1a48635353cc1db673a4bd1cd5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server-2015"></a>Configurer la réunion page jointure dans Skype pour Business Server 2015
 
**Résumé :** Apprenez à configurer la réunion page jointure dans Skype pour Business Server 2015.
  
Lorsqu’un utilisateur clique sur un lien d’une réunion dans une demande de réunion, la réunion page de jointure détecte si un Skype pour client d’entreprise est déjà installé sur l’ordinateur de l’utilisateur. Si un client est déjà installé, le client ouvre et rejoint la réunion. Si un client n’est pas installé, par défaut la 2015 version de Skype pour client d’entreprise s’ouvre. 
  
## <a name="configure-the-meeting-join-page"></a>Configurer la réunion page d’inscription

Vous pouvez modifier le comportement de la jointure de réunion si vous souhaitez permettre aux utilisateurs de participer à des conférences avec d’autres versions du client de la page. Ces options de configuration ont été retirées du Skype pour Business Server du Panneau de configuration, mais vous les configurez à l’aide de l’applet de commande Set-CsWebServiceConfiguration.
  
**Paramètres de Page joindre ensemble-CsWebServiceConfiguration de réunion**

|**Paramètre de CsWebServiceConfiguration de l’ensemble**|**Description**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Ce paramètre a été désapprouvé à utiliser avec la version locale de Skype pour Business Server 2015.  <br/> Si la valeur True, les utilisateurs se joindre à une réunion à l’aide d’une application client autre que Skype pour entreprise auront la possibilité de joindre la réunion à l’aide de l’application client en cours. La valeur par défaut est False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Ce paramètre a été désapprouvé à utiliser avec la version locale de Skype pour Business Server 2015.  <br/>  Si la valeur True, autres options pour rejoindre une conférence en ligne sont automatiquement développées et aux utilisateurs. Si la valeur False (valeur par défaut), ces options seront disponibles, mais l’utilisateur aura afficher la liste des options pour eux-mêmes.  <br/> |
   

