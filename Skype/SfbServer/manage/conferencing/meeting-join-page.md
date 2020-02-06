---
title: Configuration de la page de participation à une réunion dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Résumé : Découvrez comment configurer la page de participation à une réunion dans Skype entreprise Server.'
ms.openlocfilehash: 7381db4983b5a2c1ec6dccf474f0b381e079e222
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818515"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>Configuration de la page de participation à une réunion dans Skype entreprise Server
 
**Résumé :** En savoir plus sur la configuration de la page de participation à une réunion dans Skype entreprise Server.
  
Lorsqu’un utilisateur clique sur un lien de réunion dans une demande de réunion, la page de participation à la réunion détecte si un client Skype entreprise est déjà installé sur l’ordinateur de l’utilisateur. Si un client est déjà installé, le client ouvre et joint la réunion. Si un client n’est pas installé, le client Skype entreprise s’ouvre par défaut. 
  
## <a name="configure-the-meeting-join-page"></a>Configuration de la page de participation à une réunion

Vous pouvez modifier le comportement de la page de participation à une réunion si vous voulez permettre aux utilisateurs de participer à des réunions avec d’autres versions du client. Ces options de configuration ont été supprimées du panneau de configuration Skype entreprise Server, mais vous les configurez à l’aide de l’applet de commande Set-CsWebServiceConfiguration.
  
**Ensemble de pages de participation à une réunion-paramètres de CsWebServiceConfiguration**

|**Paramètre SET-CsWebServiceConfiguration**|**Description**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Ce paramètre a été déconseillé pour une utilisation avec la version locale de Skype entreprise Server.  <br/> Si elle est définie sur true, les utilisateurs qui rejoignent une réunion à l’aide d’une application client autre que Skype entreprise seront en mesure de rejoindre la réunion à l’aide de leur application client actuelle. La valeur par défaut est False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Ce paramètre a été déconseillé pour une utilisation avec la version locale de Skype entreprise Server.  <br/>  Si elle a la valeur true, d’autres options de participation à une conférence en ligne sont automatiquement développées et affichées aux utilisateurs. Si elle a la valeur false (valeur par défaut), les options suivantes sont disponibles, mais l’utilisateur doit afficher la liste des options pour eux-mêmes.  <br/> |
   

