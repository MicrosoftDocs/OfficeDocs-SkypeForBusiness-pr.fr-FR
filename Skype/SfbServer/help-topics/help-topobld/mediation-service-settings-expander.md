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
description: 'Dans Serveur de médiation, vous pouvez spécifier les éléments suivants :'
ms.openlocfilehash: 4535698552b918c57a8c76741ffaaef2c1b66b48
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23253794"
---
# <a name="mediation-service-settings-expander"></a>Expanseur des paramètres du service de médiation

Dans **Serveur de médiation**, vous pouvez spécifier les éléments suivants :

Si vous colocalisez le serveur de médiation sur le pool frontal ou le serveur Standard Edition server, activez la case à cocher **activé de cohabitation du serveur de médiation**. Si vous choisissez de ne pas colocaliser le serveur de médiation, il n’existe aucun paramètre définissables dans cette section.

Si vous avez activé la colocalisation du serveur de médiation, vous devez définir la plage de ports d’écoute sur le serveur de Transport Layer Security (TLS). Par défaut, il s’agit du port 5067. Si vous sélectionnez **Activer le port TCP**, vous devez définir un protocole TCP pour le serveur de médiation colocalisé. Il s’agit d’un paramètre facultatif, et vous devez vous reporter aux conditions requises de votre passerelle ou de votre réseau public commuté pour déterminer si vous en avez besoin. Par défaut, la valeur du port TCP est le port 5068.

Vous définissez les passerelles PSTN associées avec le serveur de médiation colocalisé. Si vous avez déjà défini des passerelles, ils seront disponibles à associer au serveur de médiation.

Si vous disposez de plusieurs passerelles associé à un serveur de médiation, la première passerelle associée sera la passerelle par défaut. Si vous devez sélectionner une autre passerelle comme passerelle par défaut, sélectionnez la passerelle à utiliser par défaut, puis cliquez sur **Utiliser par défaut**. Pour désélectionner la passerelle par défaut, cliquez sur **Annuler par défaut**.

Pour plus d’informations sur la définition et la configuration des paramètres pour le pool frontal Enterprise Edition ou Standard Edition server, consultez [définition et la configuration de la topologie](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) et [déploiement de serveurs de médiation et définition des homologues](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).


