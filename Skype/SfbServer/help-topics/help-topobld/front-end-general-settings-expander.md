---
title: Expanseur des paramètres généraux du serveur frontal
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FrontEndGeneralSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 8a5f21d0-f6c8-4907-9958-5ca36f702542
description: 'Pour modifier les paramètres d’un pool frontal existant ou d’un serveur Survivable Branch Server, consultez les sections suivantes :'
ms.openlocfilehash: 60e6099cb28ec564abde9506afb1a0ef70274684
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861451"
---
# <a name="front-end-general-settings-expander"></a>Expandeur des paramètres généraux du serveur frontal

Pour modifier les paramètres d’un pool frontal existant ou d’un serveur Survivable Branch Server, consultez les sections suivantes :

- Paramètres généraux

- Paramètres de résilience

- Paramètres des services Web

- Paramètres du serveur de médiation

## <a name="front-end-pool"></a>Pool frontal

Dans le cas d’un pool frontal, vous pouvez configurer les paramètres généraux, de résilience, des services web et du serveur de médiation. Pour en savoir plus, consultez les informations des sous-sections suivantes. Pour plus d’informations sur la définition et la configuration des paramètres du pool frontal, voir [Deploying Mediation Servers and Defining Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers).

### <a name="general-settings"></a>Paramètres généraux

Vous pouvez configurer les paramètres généraux suivants :

- **Nom de domaine complet (FQDN)**. Modifiez le nom de domaine complet du pool pour le changer.

- **Activer le port de surveillance de l’équilibreur de la charge matérielle**. Activez la case à cocher et entrez le numéro de port que votre équilibreur de la charge matérielle utilisera pour surveiller l’état des serveurs du pool.

- Dans **Composants et fonctionnalités**, définissez les rôles supplémentaires que vous voulez colocaliser avec ce pool. Vous pouvez configurer les paramètres suivants :

  - **Conférence**. Inclut le partage audio, vidéo et d’applications. Avec cette option sélectionnée, vous pouvez sélectionner Conférence rendez-vous (PSTN). Vous spécifiez et définissez une passerelle de réseau téléphonique commuté (PSTN) dans une sous-section ultérieure relative aux paramètres du serveur de médiation.

  - **Voix Entreprise**. Active les appels voix sur IP internes vers les combinés et appareils qualifiés et Skype Entreprise clients. Pour activer les fonctionnalités d’appel externe, vous devez inclure un serveur de médiation. Pour plus d’informations, voir la sous-section relative aux paramètres du serveur de médiation ci-dessous.

- Dans **Associations**, modifiez ou définissez les éléments suivants :

  - **Magasin SQL**. Modifiez une base de données SQL Server existante ou créez une base de données SQL Server pour contenir les bases de données du serveur frontal. Vous pouvez sélectionner une nouvelle instance SQL Server dans la liste ou créer une entrée en cliquant sur **Nouveau**.

    Sélectionnez **Activer la mise en miroir du magasin SQL Server**, puis sélectionnez le serveur à utiliser pour la mise en miroir. Cliquez sur **Nouveau** pour créer un magasin SQL Server.

    Sélectionnez **Utiliser le témoin de mise en miroir SQL Server pour activer le basculement automatique** pour sélectionner le serveur à utiliser comme témoin de mise en miroir. Cliquez sur **Nouveau** pour créer un magasin SQL Server.

  - **Partage de fichiers**. Modifiez le magasin de fichiers qu’utilise le pool frontal. Vous pouvez sélectionner un nouveau magasin de fichiers parmi ceux déjà définis en le sélectionnant dans la liste. Vous pouvez créer un magasin de fichiers en cliquant sur **Nouveau**.

    > [!IMPORTANT]
    > Avant de publier la nouvelle topologie que vous venez de définir, le serveur que vous spécifiez doit exister et être joint au domaine.

  - **Archivage**. Associez un magasin de serveurs d’archivage au pool frontal. Vous pouvez choisir à partir d’un serveur d’archivage SQL Server déjà défini en sélectionnant le serveur dans la liste, ou cliquer sur **Nouveau** pour indiquer un nouveau serveur d’archivage.

    > [!IMPORTANT]
    > Avant de publier la nouvelle topologie que vous venez de définir, le serveur que vous spécifiez doit exister et être joint au domaine.

    Sélectionnez **Activer la mise en miroir du magasin SQL Server**, puis sélectionnez le serveur à utiliser pour la mise en miroir. Cliquez sur **Nouveau** pour créer un magasin SQL Server.

    Sélectionnez **Utiliser le témoin de mise en miroir SQL Server pour activer le basculement automatique** pour sélectionner le serveur à utiliser comme témoin de mise en miroir. Cliquez sur **Nouveau** pour créer un magasin SQL Server.

  - **Activer la surveillance (enregistrement des détails des appels et mesures QoE)**. Sélectionnez cette option pour associer un magasin SQL Server au pool frontal. Vous pouvez choisir à partir d’un serveur de surveillance déjà défini en sélectionnant le serveur dans la liste, ou vous pouvez cliquer sur **Nouveau** pour indiquer un nouveau serveur de surveillance.

    Sélectionnez **Activer la mise en miroir du magasin SQL Server**, puis sélectionnez le serveur à utiliser pour la mise en miroir. Cliquez sur **Nouveau** pour créer un magasin SQL Server.

    Sélectionnez **Utiliser le témoin de mise en miroir SQL Server pour activer le basculement automatique** pour sélectionner le serveur à utiliser comme témoin de mise en miroir. Cliquez sur **Nouveau** pour créer un magasin SQL Server.

  - **Associer un pool de serveurs Edge (pour les composants médias)**. Associez un serveur Edge ou un pool de serveurs Edge au pool frontal. Vous pouvez choisir à partir d’un serveur Edge ou d’un pool de serveurs Edge déjà défini en sélectionnant le serveur dans la liste, ou cliquer sur **Nouveau** pour indiquer un nouveau serveur Edge ou un pool de serveurs Edge.

  - **Associer le pool à un serveur Office Web Apps Server** : sélectionnez cette option pour associer un serveur Office Web Apps Server au pool frontal. Sélectionnez un serveur existant dans la liste ou cliquez sur **Nouveau** pour créer un serveur Office Web Apps Server.

### <a name="resiliency"></a>Résilience

La résilience offre la récupération d’urgence et apporte une très grande disponibilité au pool. Lorsqu’il est configuré, un serveur de sauvegarde permet de prendre le relais d’un serveur en cas d’échec du serveur principal, permettant aux utilisateurs de se connecter et de communiquer. Il est possible que les utilisateurs ne disposent pas de toutes les fonctionnalités, selon les systèmes qui ont échoué sur le serveur principal.

Sélectionnez dans la liste le pool frontal ou le serveur Standard Edition Server qui agira en tant que serveur de sauvegarde pour le pool. Vous pouvez également choisir d’activer des intervalles de basculement et de secours. L’activation des paramètres d’intervalle de basculement et de secours (indiqués en secondes) permet de détecter automatiquement un serveur défaillant ; un intervalle de secours permet de déterminer automatiquement que le serveur principal est le serveur de sauvegarde.

> [!IMPORTANT]
> Lorsque vous définissez la détection d’échec et l’intervalle de secours, prenez garde à ne pas saisir un intervalle qui provoquera le basculement et le secours si le serveur ne répond pas pendant un court moment. Le serveur peut cesser de répondre pendant de courts moments en fonction du chargement du pool ou des serveurs. Les valeurs par défaut pour le basculement et le secours sont de 300 secondes et 600 secondes de pool à pool, ou de pool à serveur Standard Edition Server. Si un Survivable Branch Appliance ou un Survivable Branch Server est présent sur un site pour un pool ou un serveur Standard Edition, les valeurs par défaut sont de 120 secondes pour le basculement et de 240 secondes pour le secours.

> [!CAUTION]
> La valeur minimale de l’**intervalle de basculement** ne doit pas être inférieure à 90 secondes, sinon la valeur de 90 secondes est utilisée. Le délai de ping intercluster est de 30 secondes, et un paramètre inférieur à 90 causerait une condition selon laquelle les serveurs d’inscriptions principaux et de sauvegarde auraient un cycle montant et descendant, entraînant un impact négatif sur la production, ces derniers essayant de résoudre le statut utilisable de l’autre. Une durée inférieure à 90 secondes est insuffisante pour déterminer si le serveur d’inscription principal est disponible ou non.

### <a name="web-services"></a>Services web

Pour modifier ou spécifier un paramètre supplémentaire pour les services Web sur le pool frontal, modifiez ou spécifiez des paramètres dans **Services Web internes** et **Services Web externes**.

Dans **Services Web internes**, spécifiez les éléments suivants :

> [!CAUTION]
> Si vous avez plusieurs serveurs frontaux ou serveurs frontaux, le nom de groupe des services Web externes doit être unique. Par exemple, si vous définissez le nom de groupe des services Web externes d’un serveur frontal en tant que **pool01.contoso.com,** vous ne pouvez pas utiliser **pool01.contoso.com** pour un autre pool frontal ou serveur frontal. Si vous déployez également des directeurs, le FQDN des services Web externes défini pour n’importe quel directeur ou pool directeur doit être unique à partir de n’importe quel autre directeur ou pool directeur, ainsi que de tout pool frontal ou serveur frontal. Si vous décidez de remplacer les services web internes par un FQDN auto-défini, chaque FQDN doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool directeur.

- Si vous sélectionnez **Remplacer le nom de domaine complet**, vous pouvez indiquer un nom de domaine complet différent pour l’identité des **Services web internes** sur le pool. Par défaut, le paramètre est le nom du pool actuel tel que défini pour le pool frontal.

- Ports d’écoute et publiés pour HTTP et HTTPS nécessaires à votre déploiement. Le paramètre par défaut du port 80 pour HTTP et du port 443 pour HTTPS sont les paramètres les plus courants et ne doivent généralement pas être modifiés, à moins que vous n’ayez des exigences particulières au sein de votre organisation et de votre infrastructure.

Dans **Services web externes**, spécifiez les éléments suivants :

- Le nom de domaine complet des services Web externes. Le nom de domaine complet spécifié ici sera généralement défini par les exigences de votre connexion externe, comme le proxy inverse.

- Ports d’écoute et publiés pour HTTP et HTTPS nécessaires à votre déploiement. Les paramètres par défaut du port 8080 pour HTTP et du port 4443 pour HTTPS sont définis initialement. Vous pouvez modifier ces paramètres pour les ports d’écoute en fonction des exigences pour votre proxy inverse et de votre réseau externe. Les ports publiés sont définis par défaut sur le port 80 pour HTTP et le port 443 pour HTTPS. Ces valeurs déterminent quels seront les ports d’écoute du pool pour les demandes entrantes. En règle générale, elles n’ont pas besoin d’être modifiées, sauf en cas de conflit entre les exigences de port sur le pool. Les ports publiés internes et externes utilisant les mêmes valeurs de port sont attendus. Il ne s’agit pas d’un conflit.

### <a name="mediation-server"></a>Serveur de médiation

Dans **Serveur de médiation**, spécifiez les éléments suivants :

- Si vous colocalisez le serveur de médiation avec le pool, activez la case à cocher **Activation de la fonctionnalité de cohabitation du serveur de médiation**. Si vous choisissez de ne pas colocaliser le serveur de médiation, cette section ne comporte aucun paramètre disponible.

- Si vous activez la fonctionnalité de colocalisation du serveur de médiation, définissez la plage de ports d’écoute des serveurs du pool pour le protocole TLS (Transport Layer Security). Par défaut, ce port est 5067. Si vous sélectionnez **Activer le port TCP**, vous devez définir un protocole TCP (Transmission Control Protocol) pour le serveur de médiation colocalisé. Il s’agit d’un paramètre facultatif et vous devez vous reporter aux conditions requises de votre passerelle ou de votre réseau public commuté pour déterminer si vous en avez besoin. Par défaut, la valeur du port TCP est 5068.

- Jonctions associées au serveur de médiation colocalisé. Si vous avez déjà défini des jonctions, elles pourront être associées au serveur de médiation.

- Si plusieurs jonctions sont associées à un serveur de médiation, vous pouvez spécifier une jonction par défaut en sélectionnant la passerelle et en cliquant sur **Utiliser par défaut**. Pour désélectionner une passerelle par défaut, cliquez sur **Annuler Par défaut**.

Pour plus d’informations sur la définition et la configuration des paramètres du pool frontal, voir [Deploying Mediation Servers and Defining Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers).

## <a name="standard-edition-server"></a>Serveur Standard Edition

Pour un serveur Standard Edition, vous pouvez configurer des paramètres généraux, de résistance, des services Web et du serveur de médiation. Pour en savoir plus, consultez les informations des sous-sections suivantes. Pour plus d‘informations sur la définition et la configuration des paramètres du serveur Standard Edition, voir [Defining and Configuring the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-defining-and-configuring-the-topology) et [Deploying Mediation Servers and Defining Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers).

### <a name="general-settings"></a>Paramètres généraux

Vous pouvez configurer les paramètres généraux suivants :

- **FQDN**. Notez que le nom de domaine complet ne peut pas être modifié. Vous devez supprimer et redéfinir le serveur Standard Edition Server pour modifier le nom de domaine complet qui lui est associé.

- Choisissez **Utiliser toutes les adresses IP configurées** ou **Limiter l’utilisation des services aux adresses IP sélectionnées**. Si vous choisissez de limiter le service aux adresses IP définies, vous définirez l’adresse IP principale que le serveur utilisera pour toutes les communications, à l’exception du réseau téléphonique commuté (PSTN). Vous pouvez aussi sélectionner **Activer IPv6** pour activer IPv6 pour ce serveur.

- **Activer le port de surveillance de l’équilibreur de la charge matérielle**. Activez la case à cocher et entrez le numéro de port que votre équilibreur de la charge matérielle utilisera pour surveiller l’état du serveur.

- Dans **Composants et fonctionnalités**, définissez les rôles supplémentaires que ce serveur devra colocaliser. Vous pouvez configurer les paramètres suivants :

  - **Conférence**. Inclut le partage audio, vidéo et d’applications. Avec cette option sélectionnée, vous pouvez sélectionner **Conférence rendez-vous (PSTN)**. Vous pouvez spécifier et définir une passerelle PSTN ultérieurement dans les paramètres du serveur de médiation.

  - **Voix Entreprise**. Active les appels voix sur IP internes vers les combinés et appareils qualifiés et Skype Entreprise clients. Pour activer les fonctionnalités d’appel externe, vous devez inclure un serveur de médiation. Pour plus d’informations, voir la sous-section relative aux paramètres du serveur de médiation ci-dessous.

- Dans **Associations**, vous pouvez modifier ou spécifier les paramètres suivants :

  - Sélectionnez **Magasin SQL Server** pour associer un magasin SQL Server à un serveur frontal. Vous pouvez également activer la mise en miroir et sélectionner un serveur témoin de mise en miroir.

  - **Partage de fichiers**. Modifiez le magasin de fichiers qu’utilise le serveur Standard Edition. Vous pouvez sélectionner un nouveau magasin de fichiers parmi ceux déjà définis en le sélectionnant dans la liste. Vous pouvez créer un magasin de fichiers en cliquant sur **Nouveau**.

    > [!IMPORTANT]
    > Avant de publier la nouvelle topologie que vous venez de définir, le serveur que vous spécifiez doit exister et être joint au domaine.

  - **Archivage**. Associez un magasin SQL Server d’archivage à un serveur Standard Edition. Vous pouvez choisir à partir d’un magasin d’archivage déjà défini en sélectionnant le serveur dans la liste, ou vous pouvez cliquer sur **Nouveau** pour indiquer un nouveau serveur d’archivage.

    > [!IMPORTANT]
    > Avant de publier la nouvelle topologie que vous venez de définir, le serveur que vous spécifiez doit exister et être joint au domaine.

  - **Activer la surveillance (enregistrement des détails des appels et mesures QoE)**. Associez un serveur de surveillance à un serveur Standard Edition. Vous pouvez choisir à partir d’un serveur de surveillance déjà défini en sélectionnant le serveur dans la liste, ou cliquer sur **Nouveau** pour indiquer un nouveau serveur de surveillance.

  - **Associer le pool à un serveur Office Web Apps Server** : sélectionnez cette option pour associer un serveur Office Web Apps Server au pool frontal. Sélectionnez un serveur existant dans la liste ou cliquez sur **Nouveau** pour créer un serveur Office Web Apps Server.

  - **Associer un pool de serveurs Edge**. Associez un serveur Edge ou un pool de serveurs Edge à un serveur Standard Edition. Vous pouvez choisir à partir d’un serveur Edge ou d’un pool de serveurs Edge déjà défini en sélectionnant le serveur dans la liste, ou cliquer sur **Nouveau** pour indiquer un nouveau serveur Edge ou un pool de serveurs Edge.

### <a name="resiliency"></a>Résilience

La résilience offre la récupération d’urgence et apporte une très grande disponibilité au serveur. Lorsqu’il est configuré, un serveur de sauvegarde permet de prendre le relais d’un serveur en cas d’échec du serveur principal, permettant aux utilisateurs de se connecter et de communiquer. Il est possible que les utilisateurs ne disposent pas de toutes les fonctionnalités, selon les systèmes qui ont également échoué.

Sélectionnez dans la liste le pool frontal ou le serveur Standard Edition Server qui agira en tant que serveur de sauvegarde pour le serveur. Vous pouvez également choisir d’activer des intervalles de basculement et de secours. L’activation des paramètres d’intervalle de basculement et de secours (indiqués en secondes) permet de détecter automatiquement un serveur d’inscriptions défaillant ; un intervalle de secours permet de déterminer automatiquement que le serveur principal est le serveur de sauvegarde.

> [!IMPORTANT]
> Lorsque vous définissez la détection d’échec et l’intervalle de secours, prenez garde à ne pas saisir un intervalle qui provoquera le basculement et le secours si le serveur ne répond pas pendant un court moment. Le serveur principal peut cesser de répondre pendant de courts moments en fonction du chargement du pool ou des serveurs. Les valeurs par défaut pour le basculement et le secours sont de 300 secondes et 600 secondes de pool à pool, ou de pool à serveur Standard Edition Server. Si un Survivable Branch Appliance ou un Survivable Branch Server est présent sur un site pour un pool ou un serveur Standard Edition, les valeurs par défaut sont de 120 secondes pour le basculement et de 240 secondes pour le secours.

### <a name="web-services"></a>Services web

Pour modifier ou spécifier un paramètre supplémentaire pour les services Web sur le serveur, modifiez ou spécifiez des paramètres dans **Services Web internes** et **Services Web externes**.

Pour **Services Web internes**, vous pouvez spécifier les paramètres suivants :

- Si vous sélectionnez Remplacer le nom de domaine complet, vous pouvez indiquer un nom de domaine complet différent pour l’identité des services web internes sur le serveur. Par défaut, le paramètre est le nom du serveur actuel tel que défini pour le serveur Standard Edition Server.

- Ports d’écoute et publiés pour HTTP et HTTPS nécessaires à votre déploiement. Le paramètre par défaut du port 80 pour HTTP et du port 443 pour HTTPS sont les paramètres les plus courants et ne doivent généralement pas être modifiés, à moins que vous n’ayez des exigences particulières au sein de votre organisation et de votre infrastructure.

Dans le cas des **Services web externes**, vous pouvez spécifier les éléments suivants :

- Le nom de domaine complet des services Web externes. Le nom de domaine complet spécifié ici sera généralement défini par les exigences de votre connexion externe, comme le proxy inverse.

- Ports d’écoute pour HTTP et HTTPS nécessaires à votre déploiement. Les paramètres par défaut du port 8080 pour HTTP et du port 4443 pour HTTPS sont définis initialement. Vous pouvez modifier ces paramètres pour les ports d’écoute en fonction des exigences pour votre proxy inverse et de votre réseau externe. Ces valeurs déterminent quels seront les ports d’écoute du serveur pour les demandes entrantes. Elles ne doivent généralement pas être modifiées, sauf en cas de conflit entre les exigences en matière de port sur le serveur.

### <a name="mediation-server"></a>Serveur de médiation

Pour **Serveur de médiation**, vous pouvez spécifier les éléments suivants :

- Si vous colocalisez le serveur de médiation avec le serveur, activez la case à cocher **Activation de la fonctionnalité de cohabitation du serveur de médiation**. Si vous choisissez de ne pas colocaliser le serveur de médiation, cette section ne comporte aucun paramètre disponible.

- Si vous avez activé la colocalisation du serveur de médiation, vous définissez la plage de ports d’écoute du serveur pour le protocole TLS. Par défaut, ce port est 5067. Si vous sélectionnez **Activer le port TCP**, vous devez définir un protocole TCP pour le serveur de médiation colocalisé. Il s’agit d’un paramètre facultatif et vous devez consulter la configuration requise de votre passerelle ou de votre réseau public commuté pour déterminer si vous en avez besoin. Par défaut, la valeur du port TCP est 5068.

- Jonctions associées au serveur de médiation colocalisé. Si vous avez déjà défini des jonctions, elles pourront être associées au serveur de médiation.

- Si plusieurs passerelles sont associées à un serveur de médiation, vous pouvez spécifier une passerelle par défaut en sélectionnant la passerelle et en cliquant sur **Utiliser par défaut**. Pour désélectionner une passerelle par défaut, cliquez sur **Annuler Par défaut**.

Pour plus d’informations sur la définition et la configuration des paramètres du serveur Standard Edition, voir [Defining and Configuring the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-defining-and-configuring-the-topology) et [Deploying Mediation Servers and Defining Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers).