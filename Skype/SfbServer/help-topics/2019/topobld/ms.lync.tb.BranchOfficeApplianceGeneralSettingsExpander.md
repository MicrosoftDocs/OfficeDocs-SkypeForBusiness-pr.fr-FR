---
title: Expanseur des paramètres généraux du Branch Office Appliance
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
ROBOTS: NOINDEX, NOFOLLOW
description: 'Les sections suivantes vous permettent de modifier les paramètres d’un Survivable Branch Appliance existant ou d’un serveur Survivable Branch Server, les sections suivantes se succèdent :'
ms.openlocfilehash: 8f1ac9a0b62752fcf79f2523dbc3b9438dfba867
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62387012"
---
# <a name="branch-office-appliance-general-settings-expander"></a>Expandeur des paramètres généraux du Branch Office Appliance

Les sections suivantes vous permettent de modifier les paramètres d’un Survivable Branch Appliance existant ou d’un serveur Survivable Branch Server, les sections suivantes se succèdent :

- Paramètres généraux

- Paramètres de résilience

- Paramètres du serveur de médiation


Dans le cas d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server, vous avez accès aux sections suivantes :

### <a name="general-settings"></a>Paramètres généraux

Nom de domaine complet (FQDN) du Survivable Branch Appliance ou du serveur Survivable Branch Server. Modifiez le nom de domaine complet du serveur pour changer la valeur. Vous devez disposer d’un enregistrement DNS A (hôte) qui corresponde à la nouvelle valeur.

Vous pouvez choisir **Utiliser toutes les adresses IP configurées** ou **Limiter l’utilisation des services aux adresses IP sélectionnées**. Si vous choisissez **Limiter le service aux adresses IP définies**, vous définissez l’adresse IP principale que le serveur utilisera pour toutes les communications, à l’exception de la passerelle du réseau téléphonique commuté (PSTN). Vous devez définir une adresse IP distincte pour l’utilisation du réseau téléphonique commuté.

Dans **Associations**, vous pouvez modifier ou spécifier les paramètres suivants :

- Associer un serveur d’archivage vous permet de choisir d’associer un serveur d’archivage au Survivable Branch Appliance ou au serveur Survivable Branch Server. Vous pouvez choisir à partir d’un serveur d’archivage déjà défini en sélectionnant le serveur dans la liste drop-down, ou cliquer sur **Nouveau** pour spécifier un nouveau serveur d’archivage.

    > [!IMPORTANT]
    > Avant de publier la nouvelle topologie que vous venez de définir, le serveur que vous spécifiez doit exister et être joint au domaine.

- Associer un serveur de surveillance vous permet de choisir d’associer un serveur de surveillance au Survivable Branch Appliance ou au serveur Survivable Branch Server. Vous pouvez choisir à partir d’un serveur de surveillance déjà défini en sélectionnant le serveur dans la liste de listes ou en cliquant sur **Nouveau** pour spécifier un nouveau serveur de surveillance.

- Associer un pool de serveurs Edge vous permet de choisir d’associer un serveur Edge ou un pool de serveurs Edge au Survivable Branch Appliance ou au serveur Survivable Branch Server. Vous pouvez choisir à partir d’un serveur Edge ou d’un pool de serveurs Edge déjà défini en sélectionnant le serveur dans la liste déroulante, ou vous pouvez cliquer sur **Nouveau** pour indiquer un nouveau serveur Edge ou un pool de serveurs Edge.

### <a name="resiliency"></a>Résilience

La résilience apporte une très grande disponibilité au pool de serveurs d’inscriptions. Lorsqu’il est configuré, un serveur d’inscriptions de sauvegarde permet de prendre le relais d’un serveur d’inscriptions en cas d’échec du serveur d’inscriptions principal, permettant aux utilisateurs de se connecter et de communiquer. Il est possible que les utilisateurs ne disposent pas de toutes les fonctionnalités, selon les systèmes qui ont échoué sur le serveur d’inscriptions principal.

Dans la liste de listes listes, sélectionnez le pool frontal Êdition Entreprise ou le serveur frontal Édition Standard qui agit en tant que serveur d’inscriptions de sauvegarde pour le Survivable Branch Appliance ou le serveur Survivable Branch Server. Vous pouvez également choisir d’activer des intervalles de basculement et de secours. L’activation des paramètres d’intervalle de basculement et de secours (indiqués en secondes) permet de détecter automatiquement un serveur d’inscriptions défaillant ; un intervalle de secours permet de déterminer automatiquement que le serveur principal est le serveur de sauvegarde et qu’il peut reprendre le processus du serveur d’inscriptions.

> [!IMPORTANT]
> Lorsque vous définissez l’intervalle entre deux détections d’échec et de secours, prenez garde à ne pas entrer un intervalle qui provoquera le basculement et le secours si le serveur d’inscriptions ne répond pas pendant un court moment. Le serveur d’inscriptions peut cesser de répondre pendant de courts moments en fonction du chargement du pool ou des serveurs. Les valeurs par défaut d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server dans un site pour un pool ou un serveur frontal Édition Standard sont de 120 secondes pour leover et de 240 secondes pour le serveur de base.

### <a name="mediation-server"></a>Serveur de médiation

Dans le cas du **Serveur de médiation**, vous pouvez spécifier les éléments suivants :

La case à cocher **Activation de la fonctionnalité de cohabitation du serveur de médiation** n’est pas active sur un Survivable Branch Appliance ou un serveur Survivable Branch Server car le serveur de médiation est colocalisé.

Vous définissez le port d’écoute sur les serveurs du pool pour le protocole TLS (Transport Layer Security). Par défaut, ce port est 5067. Si vous sélectionnez **Activer le port TCP**, vous devez définir un protocole TCP pour le serveur de médiation colocalisé. Il s’agit d’un paramètre facultatif et vous devez consulter la configuration requise de votre passerelle ou de votre réseau public commuté pour déterminer si vous en avez besoin. Par défaut, la valeur du port TCP est 5068.

Vous définissez des passerelles PSTN qui sont associées au serveur de médiation colocalisé. Si vous avez déjà défini des passerelles, ces dernières pourront être associées au serveur de médiation. Si vous n’avez défini aucune passerelle, mais si elles sont disponibles pour la définition, vous pouvez sélectionner **Nouveau**. Vous pouvez supprimer des passerelles qui sont déjà configurées pour ce serveur de médiation. Sélectionnez la passerelle, puis cliquez sur **Supprimer**.

Si plusieurs passerelles sont associées à un serveur de médiation, la première passerelle associée sera la passerelle par défaut. Si vous devez choisir une autre passerelle comme passerelle par défaut, sélectionnez la passerelle que vous souhaitez utiliser par défaut, puis cliquez sur **Utiliser par défaut**.


Pour plus d’informations sur la définition et la configuration des paramètres du Survivable Branch Appliance ou du serveur Survivable Branch Server, voir [Branch-Site Resiliency Solutions](/previous-versions/office/lync-server-2013/lync-server-2013-branch-site-resiliency-solutions).