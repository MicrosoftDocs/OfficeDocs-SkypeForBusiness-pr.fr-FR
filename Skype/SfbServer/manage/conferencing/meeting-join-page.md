---
title: Configurer la page de réunion dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Résumé : Découvrez comment configurer la page de réunion dans Skype Entreprise Server.'
ms.openlocfilehash: d1615b2d436cf884ee8d37e911b7ca82c57289973279c6f98f4360a6a40d99e0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54313222"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>Configurer la page de réunion dans Skype Entreprise Server
 
**Résumé :** Découvrez comment configurer la page de rejoindre une réunion dans Skype Entreprise Server.
  
Lorsqu’un utilisateur clique sur un lien de réunion dans une demande de réunion, la page de réunion détecte si un client Skype Entreprise est déjà installé sur l’ordinateur de l’utilisateur. Si c’est le cas, ce client s’ouvre et se joint à la réunion. Si un client n’est pas installé, le client Skype Entreprise s’ouvre par défaut. 
  
## <a name="configure-the-meeting-join-page"></a>Configuration de la page de participation à une réunion

Vous pouvez modifier le comportement de la page de rejoindre la réunion si vous souhaitez autoriser les utilisateurs à participer à des réunions avec d’autres versions du client. Ces options de configuration ont été supprimées du Panneau de configuration Skype Entreprise Server, mais vous les configurez à l’aide de l'Set-CsWebServiceConfiguration de commande.
  
**Paramètres de la page de Set-CsWebServiceConfiguration réunion**

|**Paramètre Set-CsWebServiceConfiguration**|**Description**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Ce paramètre a été supprimé pour être utilisé avec la version sur site de Skype Entreprise Server.  <br/> Si la valeur est True, les utilisateurs qui rejoignent une réunion à l’aide d’une application cliente autre que Skype Entreprise auront la possibilité de participer à la réunion à l’aide de leur application cliente actuelle. La valeur par défaut est False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Ce paramètre a été supprimé pour être utilisé avec la version sur site de Skype Entreprise Server.  <br/>  Si la valeur est True, les autres options de rejoindre une conférence en ligne sont automatiquement étendues et affichées aux utilisateurs. Si la valeur est False (valeur par défaut), ces options seront disponibles, mais l’utilisateur devra afficher la liste des options pour lui-même.  <br/> |
   

