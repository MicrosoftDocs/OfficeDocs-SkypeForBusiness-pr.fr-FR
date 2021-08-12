---
title: Expanseur des paramètres du service de médiation
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour le serveur de médiation, vous pouvez spécifier les données suivantes :'
ms.openlocfilehash: 2ef7e506e6c3409cdb1dbfa8abd59d9e3fa6b6540c55ffac6e69d34c29e1b82b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54291292"
---
# <a name="mediation-service-settings-expander"></a>Expandeur des paramètres du service de médiation

Pour **Serveur de médiation**, vous pouvez spécifier les éléments suivants :

Si vous coloquez le serveur de médiation sur le pool frontal ou le serveur Édition Standard, activez la case à cocher Serveur de médiation **cochez la case.** Si vous choisissez de ne pas colocaliser le serveur de médiation, cette section ne comporte aucun paramètre définissable.

Si vous avez activé la colocalisation du serveur de médiation, vous devez définir la plage de ports d’écoute du serveur pour le protocole TLS (Transport Layer Security). Par défaut, ce port est 5067. Si vous sélectionnez **Activer le port TCP**, vous devez définir un protocole TCP (Transmission Control Protocol) pour le serveur de médiation colocalisé. Il s’agit d’un paramètre facultatif et vous devez vous reporter aux conditions requises de votre passerelle ou de votre réseau public commuté pour déterminer si vous en avez besoin. Par défaut, la valeur du port TCP est 5068.

Vous définissez les passerelles PSTN qui sont associées au serveur de médiation colocalisé. Si vous avez déjà défini des passerelles, ces dernières pourront être associées au serveur de médiation.

Si plusieurs passerelles sont associées à un serveur de médiation, la première passerelle associée sera la passerelle par défaut. Si vous devez choisir une autre passerelle comme passerelle par défaut, sélectionnez la passerelle que vous souhaitez utiliser par défaut, puis cliquez sur **Utiliser par défaut**. Pour désélectionner la passerelle par défaut, cliquez sur **Annuler Par défaut**.

Pour plus d’informations sur la définition et la configuration des paramètres du pool frontal Êdition Entreprise ou du serveur Édition Standard, voir [Defining and Configuring the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-defining-and-configuring-the-topology) and [Deploying Mediation Servers and Defining Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers).