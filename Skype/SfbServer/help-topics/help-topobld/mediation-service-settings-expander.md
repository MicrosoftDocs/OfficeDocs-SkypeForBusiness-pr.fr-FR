---
title: Expanseur des paramètres du service de médiation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 'Dans Serveur de médiation, vous pouvez spécifier les éléments suivants :'
ms.openlocfilehash: fcff87faeb5911d12806f80499c2b2f0d63caff3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285602"
---
# <a name="mediation-service-settings-expander"></a>Expanseur des paramètres du service de médiation

Dans **Serveur de médiation**, vous pouvez spécifier les éléments suivants :

Si vous êtes collocating du serveur de médiation sur le pool frontal ou sur le serveur Standard Edition Server, activez la case à cocher Activer le **serveur de médiation**. Si vous choisissez de ne pas collocater le serveur de médiation, il n’y a aucun paramètre définissable dans cette section.

Si vous avez activé la colocalisation du serveur de médiation, vous devez définir la plage de port d’écoute sur le serveur pour le protocole TLS (Transport Layer Security). Par défaut, il s’agit du port 5067. Si vous sélectionnez **Activer le port TCP**, vous devez définir un protocole TCP pour le serveur de médiation colocalisé. Il s’agit d’un paramètre facultatif, et vous devez vous reporter aux conditions requises de votre passerelle ou de votre réseau public commuté pour déterminer si vous en avez besoin. Par défaut, la valeur du port TCP est le port 5068.

Vous définissez des passerelles RTC associées au serveur de médiation colocalisé. Si vous avez déjà défini des passerelles, celles-ci sont disponibles pour être associées au serveur de médiation.

Si vous avez plusieurs passerelles associées à un serveur de médiation, la première passerelle associée sera la passerelle par défaut. Si vous devez sélectionner une autre passerelle comme passerelle par défaut, sélectionnez la passerelle à utiliser par défaut, puis cliquez sur **Utiliser par défaut**. Pour désélectionner la passerelle par défaut, cliquez sur **Annuler par défaut**.

Pour plus d’informations sur la définition et la configuration des paramètres du pool frontal Enterprise Edition ou du serveur Standard Edition Server, voir [définition et configuration de la topologie](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) et [déploiement de serveurs de médiation et définition](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)d’homologues.


