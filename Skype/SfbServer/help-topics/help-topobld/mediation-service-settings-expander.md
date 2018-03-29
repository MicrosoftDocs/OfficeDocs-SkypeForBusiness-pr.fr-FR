---
title: Expanseur des paramètres du service de médiation
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 'Serveur de médiation, vous pouvez spécifier les éléments suivants :'
ms.openlocfilehash: e322b2ffd383c2bd0170852a6fec6c3122251700
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="mediation-service-settings-expander"></a>Expanseur des paramètres du service de médiation
 
Dans **Serveur de médiation**, vous pouvez spécifier les éléments suivants :
  
Si vous sont COLLOCATION sur le pool frontal, le serveur de médiation ou le serveur Standard Edition server, activez la case à cocher **serveur de médiation colocalisés activé**. Si vous choisissez de ne pas colocaliser le serveur de médiation, il n’y a pas de paramètres définis dans cette section. 
  
Si vous avez activé la colocalisation du serveur de médiation, vous devez définir la plage de ports à l’écoute sur le serveur de sécurité TLS (Transport Layer). Par défaut, il s’agit du port 5067. Si vous sélectionnez **Activer le port TCP**, vous devez définir un protocole TCP pour le serveur de médiation colocalisé. Il s’agit d’un paramètre facultatif, et vous devez vous reporter aux conditions requises de votre passerelle ou de votre réseau public commuté pour déterminer si vous en avez besoin. Par défaut, la valeur du port TCP est le port 5068.
  
Vous définissez les passerelles RTPC qui sont associés au serveur de médiation colocalisée. Si vous avez déjà défini des passerelles, ils seront disponibles à associer avec le serveur de médiation. 
  
Si vous avez plus d’une passerelle associée à un serveur de médiation, la première passerelle associée sera la passerelle par défaut. Si vous devez sélectionner une autre passerelle comme passerelle par défaut, sélectionnez la passerelle à utiliser par défaut, puis cliquez sur **Utiliser par défaut**. Pour désélectionner la passerelle par défaut, cliquez sur **Annuler par défaut**.
  
Pour plus d’informations sur la définition et la configuration des paramètres pour le serveur Standard Edition server ou le pool frontal de Enterprise Edition, consultez [définition et configuration de la topologie](http://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) et le [déploiement de serveurs de médiation et de définir des homologues](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).
  

