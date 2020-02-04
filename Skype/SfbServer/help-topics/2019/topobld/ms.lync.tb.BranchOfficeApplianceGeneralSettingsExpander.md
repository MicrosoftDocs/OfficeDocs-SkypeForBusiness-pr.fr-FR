---
title: Expanseur des paramètres généraux du Branch Office Appliance
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour modifier les paramètres d’une unité de branche Survivable existante ou d’un serveur de succursales survivant, vous avez accès aux sections suivantes :'
ms.openlocfilehash: 97f12828a8513ce284f4cd14c06de3496100c313
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702389"
---
# <a name="branch-office-appliance-general-settings-expander"></a>Expanseur des paramètres généraux du Branch Office Appliance

Pour modifier les paramètres d’une unité de branche Survivable existante ou d’un serveur de succursales survivant, vous avez accès aux sections suivantes :

- Paramètres généraux

- Paramètres de résilience

- Paramètres du serveur de médiation


Dans le cas d’une unité de branchement ou d’un serveur de succursale survivant, vous pouvez obtenir les éléments suivants :

### <a name="general-settings"></a>Paramètres généraux

Nom de domaine complet (FQDN) de l’appareil de branchement survivant ou du serveur de succursales survivant. Modifiez le nom de domaine complet du serveur pour changer la valeur. Vous devez disposer d’un enregistrement d’hôte DNS (A) correspondant à la nouvelle valeur.

Vous pouvez sélectionner **Utiliser toutes les adresses IP configurées** ou **Limiter l’utilisation des services aux adresses IP sélectionnées**. Si vous sélectionnez **Limiter le service aux adresses IP définies**, vous définissez l’adresse IP principale utilisée par le serveur pour toutes les communications, à l’exception de la passerelle du réseau téléphonique commuté (RTC). Vous devez définir une adresse IP distincte pour l’utilisation du réseau téléphonique commuté.

Dans **Associations**, vous pouvez modifier ou spécifier les paramètres suivants :

- Associate Server Associates vous permet de sélectionner l’Association d’un serveur d’archivage à l’appareil de succursales survivant ou à un serveur de succursales survivant. Vous pouvez effectuer une sélection à partir d’un serveur d’archivage déjà défini en sélectionnant le serveur dans la liste déroulante, ou en cliquant sur **nouveau** pour spécifier un nouveau serveur d’archivage.

    > [!IMPORTANT]
    > Avant de publier la nouvelle topologie que vous venez de définir, le serveur que vous spécifiez doit exister et être joint au domaine.

- L’option associer le serveur de surveillance vous permet d’associer un serveur de surveillance à l’appareil de succursales survivant ou au serveur de succursales survivant. Vous pouvez sélectionner un serveur de surveillance déjà défini en le sélectionnant dans la liste déroulante ou en cliquant sur **nouveau** pour spécifier un nouveau serveur de surveillance.

- Le pool d’entreprise Associate vous permet d’associer un serveur Edge ou un pool à un serveur Edge ou à un serveur de succursales survivant. Vous pouvez sélectionner le serveur dans la liste déroulante à partir d’un serveur Edge ou d’un pool de serveurs Edge déjà défini ou cliquer sur **Nouveau** pour spécifier un nouveau serveur Edge ou un nouveau pool de serveurs Edge.

### <a name="resiliency"></a>Résilience

La résilience permet une très grande disponibilité du pool de serveurs d’inscriptions. Lorsqu’un serveur d’inscriptions de secours est configuré, il permet de prendre le relais d’un serveur d’inscriptions en cas d’échec du serveur d’inscriptions principal, ce qui permet aux utilisateurs de se connecter et de communiquer. Certains utilisateurs peuvent disposer de fonctionnalités réduites en fonction des systèmes qui ont échoué sur le serveur principal.

Dans la liste déroulante, sélectionnez le serveur frontal Enterprise Edition ou le serveur frontal Standard Edition qui jouera le rôle d’bureau d’enregistrement de sauvegarde de l’appareil de succursale survivant ou du serveur de succursales survivant. Vous pouvez également activer l’intervalle de reprise et de secours. L’activation des paramètres de basculement et de basculement (spécifiés en secondes) permet la détection automatique d’un bureau d’enregistrement en échec et un délai de basculement pour permettre la détermination automatique de la sauvegarde du serveur principal et peut prendre en charge le processus d’inscription.

> [!IMPORTANT]
> Lorsque vous définissez l’intervalle entre deux détections d’échec et de secours, veillez à ne pas entrer un intervalle qui entraînera le basculement et le secours si le serveur d’inscriptions ne répond pas pendant un court instant. Le serveur d’inscriptions peut cesser de répondre pendant de brefs instants en fonction du chargement du pool ou des serveurs. Les valeurs par défaut d’une unité de branchement Survivable ou d’un serveur de succursales survivant dans un site vers un pool ou un serveur frontal Standard Edition correspond à 120 secondes pour le basculement et 240 secondes pour le secours.

### <a name="mediation-server"></a>Serveur de médiation

Dans **Serveur de médiation**, vous pouvez spécifier les éléments suivants :

La case à cocher du **serveur de médiation en option activé** n’est pas disponible sur un appareil de branche Survivable ou un serveur de succursales survivant, car le serveur de médiation est colocalisé.

Vous définissez le port d’écoute sur les serveurs du pool pour le protocole TLS (Transport Layer Security). Par défaut, il s’agit du port 5067. Si vous sélectionnez **Activer le port TCP**, vous devez définir un protocole TCP pour le serveur de médiation colocalisé. Il s’agit d’un paramètre facultatif, et vous devez consulter la configuration requise de votre passerelle ou de votre réseau public commuté pour déterminer si vous en avez besoin. Par défaut, le port TCP est le port 5068.

Vous définissez des passerelles RTC associées au serveur de médiation colocalisé. Si vous avez déjà défini des passerelles, celles-ci sont disponibles pour être associées au serveur de médiation. Si vous n’avez pas défini de passerelle, mais que vous pouvez les définir, vous pouvez sélectionner **Nouveau**. Vous pouvez également supprimer des passerelles déjà configurées pour ce serveur de médiation. Sélectionnez la passerelle, puis cliquez sur **Supprimer**.

Si vous avez plusieurs passerelles associées à un serveur de médiation, la première passerelle associée sera la passerelle par défaut. Si vous devez choisir une autre passerelle comme passerelle par défaut, sélectionnez la passerelle à utiliser par défaut, puis cliquez sur **Utiliser par défaut**.


Pour plus d’informations sur la définition et la configuration des paramètres de l’application de succursales Survivables ou du serveur de succursales survivant, voir [solutions de résilience de succursale](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx).


