---
title: Expanseur des paramètres généraux du serveur frontal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FrontEndGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a5f21d0-f6c8-4907-9958-5ca36f702542
description: 'Pour modifier les paramètres d’un pool frontal existant ou d’un serveur Survivable Branch Server, consultez les sections suivantes :'
ms.openlocfilehash: bd4cbb507bff025f7133673c25f59beada37aeb5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284409"
---
# <a name="front-end-general-settings-expander"></a>Expanseur des paramètres généraux du serveur frontal

Pour modifier les paramètres d’un pool frontal existant ou d’un serveur Survivable Branch Server, consultez les sections suivantes :

- Paramètres généraux

- Paramètres de résilience

- Paramètres des services web

- Paramètres du serveur de médiation

## <a name="front-end-pool"></a>Pool frontal

Dans le cas d’un pool frontal, vous pouvez configurer les paramètres généraux, de résilience, des services web et du serveur de médiation. Pour plus d’informations, reportez-vous aux informations des sous-sections suivantes. Pour plus d’informations sur la définition et la configuration des paramètres du pool frontal, reportez-vous à la rubrique [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).

### <a name="general-settings"></a>Paramètres généraux

Vous pouvez configurer les paramètres généraux suivants :

- **Nom de domaine complet (FQDN)**  : modifiez le nom de domaine complet du pool.

- **Activer le port de surveillance de l’équilibreur de la charge matérielle** : activez la case à cocher et entrez le numéro de port utilisé par votre équilibreur de la charge matérielle pour surveiller l’état des serveurs du pool.

- Dans **Composants et fonctionnalités**, définissez les autres rôles à colocaliser avec ce pool. Vous pouvez configurer les paramètres suivants :

  - **Conférence** : inclut le partage audio, vidéo et d’applications. Avec cette option sélectionnée, vous pouvez sélectionner Conférence rendez-vous (RTC). Vous spécifiez et définissez une passerelle de réseau téléphonique commuté (RTC) dans la sous-section Paramètres du serveur de médiation ci-dessous.

  - **Voix entreprise**. Autorise les appels voix sur IP internes vers des combinés et des appareils et des clients Skype entreprise. Pour activer les fonctionnalités d’appel externe, vous devez inclure un serveur de médiation. Pour plus d’informations, consultez la section «serveur de médiation» plus loin dans cette rubrique.

- Dans **Associations**, modifiez ou définissez les éléments suivants :

  - **Magasin SQL** : modifiez une base de données SQL Server existante ou créez une base de données SQL Server pour contenir les bases de données du serveur frontal. Vous pouvez sélectionner une nouvelle instance SQL Server dans la liste ou créer une entrée en cliquant sur **Nouveau**.

    Sélectionnez **Activer la mise en miroir du magasin SQL Server**, puis sélectionnez le serveur à utiliser pour la mise en miroir. Cliquez sur **Nouveau** pour créer un magasin SQL Server.

    Sélectionnez **Utiliser le témoin de mise en miroir SQL Server pour activer le basculement automatique** pour sélectionner le serveur servant de témoin de mise en miroir. Cliquez sur **Nouveau** pour créer un magasin SQL Server.

  - **Partage de fichiers** : modifiez le magasin de fichiers utilisé par le pool frontal. Vous pouvez sélectionner un nouveau magasin de fichiers dans la liste des magasins déjà définis ou créer un magasin de fichiers en cliquant sur **Nouveau**.

    > [!IMPORTANT]
    > Avant de publier la nouvelle topologie que vous venez de définir, le serveur que vous spécifiez doit exister et être joint au domaine.

  - **Archivage** : associez un magasin de serveurs d’archivage au pool frontal. Vous pouvez sélectionner le serveur dans la liste à partir d’un serveur d’archivage SQL Server déjà défini ou cliquer sur **Nouveau** pour spécifier un nouveau serveur d’archivage.

    > [!IMPORTANT]
    > Avant de publier la nouvelle topologie que vous venez de définir, le serveur que vous spécifiez doit exister et être joint au domaine.

    Sélectionnez **Activer la mise en miroir du magasin SQL Server**, puis sélectionnez le serveur à utiliser pour la mise en miroir. Cliquez sur **Nouveau** pour créer un magasin SQL Server.

    Sélectionnez **Utiliser le témoin de mise en miroir SQL Server pour activer le basculement automatique** pour sélectionner le serveur servant de témoin de mise en miroir. Cliquez sur **Nouveau** pour créer un magasin SQL Server.

  - **Activer la surveillance (enregistrement des détails des appels et mesures QoE)**  : sélectionnez cette option pour associer un magasin SQL Server au pool frontal. Vous pouvez sélectionner le serveur dans la liste à partir d’un serveur de surveillance déjà défini ou cliquer sur **Nouveau** pour spécifier un nouveau serveur de surveillance.

    Sélectionnez **Activer la mise en miroir du magasin SQL Server**, puis sélectionnez le serveur à utiliser pour la mise en miroir. Cliquez sur **Nouveau** pour créer un magasin SQL Server.

    Sélectionnez **Utiliser le témoin de mise en miroir SQL Server pour activer le basculement automatique** pour sélectionner le serveur servant de témoin de mise en miroir. Cliquez sur **Nouveau** pour créer un magasin SQL Server.

  - **Associer un pool de serveurs Edge (pour les composants médias)**  : associez un serveur Edge ou un pool de serveurs Edge au pool frontal. Vous pouvez sélectionnez le serveur dans la liste à partir d’un serveur Edge ou d’un pool de serveurs Edge déjà défini ou cliquer sur **Nouveau** pour spécifier un nouveau serveur Edge ou un pool de serveurs Edge.

  - **Associer le pool à un serveur Office Web Apps Server** : sélectionnez cette option pour associer un serveur Office Web Apps Server au pool frontal. Sélectionnez un serveur existant dans la liste ou cliquez sur **Nouveau** pour créer un serveur Office Web Apps Server.

### <a name="resiliency"></a>Résilience

La résilience permet la récupération d’urgence et une très grande disponibilité du pool. Lorsqu’un serveur de secours est configuré, il permet de prendre le relais d’un serveur en cas d’échec du serveur principal, ce qui permet aux utilisateurs de se connecter et de communiquer. Certains utilisateurs peuvent disposer de fonctionnalités réduites en fonction des systèmes qui ont échoué sur le serveur principal.

Dans la liste, sélectionnez le pool frontal ou le serveur Standard Edition Server qui servira de serveur de secours pour le pool. Vous pouvez également choisir d’activer des intervalles de basculement et de secours. L’activation des paramètres d’intervalle de basculement et de secours (exprimés en secondes) permet de détecter automatiquement un serveur défaillant. Un intervalle de secours permet de déterminer automatiquement que le serveur principal est le serveur de secours.

> [!IMPORTANT]
> Lorsque vous définissez la détection d’échec et l’intervalle de secours, veillez à ne pas entrer un intervalle qui entraînera le basculement et le secours en l’absence de réponse du serveur pendant un court instant. Le serveur peut cesser de répondre pendant de brefs instants en fonction du chargement du pool ou des serveurs. Les valeurs par défaut pour le basculement et le secours sont de 300 secondes et 600 secondes de pool à pool ou de pool à serveur Standard Edition Server. Si un Survivable Branch Appliance ou un Survivable Branch Server est présent sur un site pour un pool ou un serveur Standard Edition, les valeurs par défaut sont de 120 secondes pour le basculement et de 240 secondes pour le secours.

> [!CAUTION]
> La valeur minimale de l’**intervalle de basculement** ne doit pas être inférieure à 90 secondes. Si vous la définissez sur une valeur inférieure à 90 secondes, une valeur de 90 secondes est utilisée. Le délai de ping entre les clusters est de 30 secondes, et un paramètre inférieur à 90 secondes peut entraîner l’activation et la désactivation du serveur principal et du serveur de secours. Cela aurait un impact négatif sur la production, car les serveurs essaieraient de résoudre le statut utilisable de l’autre. Une durée inférieure à 90 secondes ne suffit pas pour déterminer si le serveur principal est disponible ou non.

### <a name="web-services"></a>services web

Pour modifier ou spécifier un autre paramètre pour les services web sur le pool frontal, modifiez ou spécifiez des paramètres dans **Services web internes** et **Services web externes**.

Dans **Services web internes**, spécifiez les éléments suivants :

> [!CAUTION]
> Si vous avez plusieurs pools frontal ou serveur principal, le nom de domaine complet des services Web externes doit être unique. Par exemple, si vous définissez le nom de domaine complet des services Web externes d’un serveur frontal en tant que **pool01.contoso.com**, vous ne pouvez pas utiliser **pool01.contoso.com** pour un autre pool frontal ou serveur frontal. Si vous déployez également des directeurs, le nom de domaine complet des services Web externes défini pour n’importe quel directeur ou pool de réalisateur doit être unique à partir d’un autre directeur ou pool de réalisateurs, ainsi que de n’importe quel pool frontal ou serveur frontal. Si vous décidez de remplacer les services Web internes par un nom de domaine complet autonome, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool de réalisateurs.

- Si vous sélectionnez **Remplacer le nom de domaine complet**, vous pouvez spécifier un nom de domaine complet différent pour l’identité des **services web internes** sur le pool. Par défaut, le paramètre est le nom du pool actuel défini pour le pool frontal.

- Ports d’écoute et publiés pour HTTP et HTTPS nécessaires à votre déploiement. Les paramètres par défaut, le port 80 pour le protocole HTTP et le port 443 pour le protocole HTTPS, sont les paramètres les plus courants. Ils ne doivent généralement pas être modifiés sauf si votre organisation et votre infrastructure impliquent des exigences spécifiques.

Dans **Services web internes**, spécifiez les éléments suivants :

- Le nom de domaine complet des services web externes. Le nom de domaine complet spécifié ici sera généralement défini par les exigences de votre connexion externe, comme le proxy inverse.

- Les ports d’écoute et publiés pour HTTP et HTTPS nécessaires à votre déploiement. Les paramètres par défaut, le port 8080 pour le protocole HTTP et le port 4443 pour le protocole HTTPS, sont définis initialement. Vous pouvez modifier ces paramètres pour les ports d’écoute en fonction des exigences de votre proxy inverse et de votre réseau externe. Les ports publiés sont définis par défaut sur le port 80 pour le protocole HTTP et sur le port 443 pour le protocole HTTPS. Ces valeurs déterminent les ports d’écoute du pool pour les demandes entrantes. En règle générale, celles-ci n’ont pas besoin d’être modifiées, sauf s’il y a des conflits de port requis sur le pool. Il est attendu que les ports publiés internes et externes utilisent les mêmes valeurs de port. Cela n’entraîne aucun conflit.

### <a name="mediation-server"></a>serveur de médiation

Dans **Serveur de médiation**, spécifiez les éléments suivants :

- Si vous colocalisez le serveur de médiation avec le pool, activez la case à cocher **Activation de la colocalisation du serveur de médiation**. Si vous choisissez de ne pas colocaliser le serveur de médiation, cette section ne comporte aucun paramètre disponible.

- Si vous activez la colocalisation du serveur de médiation, définissez la plage de ports d’écoute des serveurs du pool pour le protocole TLS (Transport Layer Security). Par défaut, il s’agit du port 5067. Si vous sélectionnez **Activer le port TCP**, vous devez définir un protocole TCP pour le serveur de médiation colocalisé. Il s’agit d’un paramètre facultatif, et vous devez vous reporter aux conditions requises de votre passerelle ou de votre réseau public commuté pour déterminer si vous en avez besoin. Par défaut, le port TCP est le port 5068.

- Jonctions associées au serveur de médiation colocalisé. Si vous avez déjà défini des jonctions, elles pourront être associées au serveur de médiation.

- Si plusieurs jonctions sont associées à un serveur de médiation, vous pouvez spécifier une jonction par défaut en sélectionnant la passerelle et en cliquant sur **Utiliser par défaut**. Pour désélectionner une passerelle par défaut, cliquez sur **Annuler par défaut**.

Pour plus d’informations sur la définition et la configuration des paramètres du pool frontal, reportez-vous à la rubrique [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).

## <a name="standard-edition-server"></a>Serveur Standard Edition

Dans le cas d’un serveur Standard Edition, vous pouvez configurer des paramètres généraux, de résilience, des services web et du serveur de médiation. Pour plus d’informations, reportez-vous aux informations des sous-sections suivantes. Pour plus d’informations sur la définition et la configuration des paramètres du serveur Standard Edition, reportez-vous aux rubriques [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) et [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).

### <a name="general-settings"></a>Paramètres généraux

Vous pouvez configurer les paramètres généraux suivants :

- **Nom de domaine complet**. Notez que le nom de domaine complet ne peut pas être modifié. Pour modifier le nom de domaine complet associé, vous devez supprimer et redéfinir le serveur Standard Edition Server.

- Sélectionnez **Utiliser toutes les adresses IP configurées** ou **Limiter l’utilisation des services aux adresses IP sélectionnées**. Si vous choisissez de limiter le service aux adresses IP définies, vous définirez l’adresse IP principale utilisée par le serveur pour toutes les communications, à l’exception du réseau téléphonique commuté (RTC). Vous pouvez également sélectionner **Activer IPv6** pour activer le protocole IPv6 pour ce serveur.

- **Activer le port de surveillance de l’équilibreur de la charge matérielle** : activez la case à cocher et entrez le numéro de port utilisé par votre équilibreur de la charge matérielle pour surveiller l’état du serveur.

- Dans **Composants et fonctionnalités**, définissez les autres rôles que vous voulez colocaliser avec ce serveur. Vous pouvez configurer les paramètres suivants :

  - **Conférence** : inclut le partage audio, vidéo et d’applications. Cette option étant sélectionnée, vous pouvez sélectionner **Conférence rendez-vous (RTC)**. Vous pouvez spécifier et définir une passerelle RTC par la suite dans les paramètres du serveur de médiation.

  - **Voix entreprise**. Autorise les appels voix sur IP internes vers des combinés et des appareils et des clients Skype entreprise. Pour activer les fonctionnalités d’appel externe, vous devez inclure un serveur de médiation. Pour plus d’informations, consultez la section «serveur de médiation» plus loin dans cette rubrique.

- Dans **Associations**, vous pouvez modifier ou spécifier les paramètres suivants :

  - Sélectionnez **Magasin SQL Server** pour associer un magasin SQL Server à un serveur frontal. Vous pouvez également activer la mise en miroir et sélectionner un serveur témoin de mise en miroir.

  - **Partage de fichiers** : modifiez le magasin de fichiers utilisé par le serveur Standard Edition. Vous pouvez sélectionner un nouveau magasin de fichiers dans la liste des magasins de fichiers déjà définis. Vous pouvez créer un magasin de fichiers en cliquant sur **Nouveau**.

    > [!IMPORTANT]
    > Avant de publier la nouvelle topologie que vous venez de définir, le serveur que vous spécifiez doit exister et être joint au domaine.

  - **Archivage** : associez un magasin SQL Server d’archivage à un serveur Standard Edition. Vous pouvez sélectionner le serveur dans la liste à partir d’un magasin d’archivage déjà défini ou cliquer sur **Nouveau** pour spécifier un nouveau serveur d’archivage.

    > [!IMPORTANT]
    > Avant de publier la nouvelle topologie que vous venez de définir, le serveur que vous spécifiez doit exister et être joint au domaine.

  - **Activer la surveillance (enregistrement des détails des appels et mesures QoE)**  : associez un serveur de surveillance à un serveur Standard Edition. Vous pouvez sélectionner le serveur dans la liste à partir d’un serveur de surveillance déjà défini ou cliquer sur **Nouveau** pour spécifier un nouveau serveur de surveillance.

  - **Associer le pool à un serveur Office Web Apps Server** : sélectionnez cette option pour associer un serveur Office Web Apps Server au pool frontal. Sélectionnez un serveur existant dans la liste ou cliquez sur **Nouveau** pour créer un serveur Office Web Apps Server.

  - **Associer un pool de serveurs Edge** : associez un serveur Edge ou un pool de serveurs Edge à un serveur Standard Edition. Vous pouvez sélectionner le serveur dans la liste à partir d’un serveur Edge ou d’un pool de serveurs Edge déjà défini ou cliquer sur **Nouveau** pour spécifier un nouveau serveur Edge ou un pool de serveurs Edge.

### <a name="resiliency"></a>Résilience

La résilience permet la récupération d’urgence et une très grande disponibilité du serveur. Lorsqu’un serveur de secours est configuré, il permet de prendre le relais d’un serveur en cas d’échec du serveur principal, permettant aux utilisateurs de se connecter et de communiquer. Certains utilisateurs peuvent disposer de fonctionnalités réduites en fonction des systèmes qui ont également échoué.

Dans la liste, sélectionnez le pool frontal ou le serveur Standard Edition Server qui servira de serveur de secours pour le serveur. Vous pouvez également choisir d’activer des intervalles de basculement et de secours. L’activation des paramètres d’intervalle de basculement et de secours (exprimés en secondes) permet de détecter automatiquement un serveur d’inscriptions défaillant. Un intervalle de secours permet de déterminer automatiquement que le serveur principal est le serveur de secours.

> [!IMPORTANT]
> Lorsque vous définissez la détection d’échec et l’intervalle de secours, veillez à ne pas saisir un intervalle qui entraînera le basculement et le secours si le serveur ne répond pas pendant un court instant. Le serveur principal peut cesser de répondre pendant de brefs instants en fonction du chargement du pool ou des serveurs. Les valeurs par défaut pour le basculement et le secours sont de 300 secondes et 600 secondes de pool à pool ou de pool à serveur Standard Edition Server. Si un Survivable Branch Appliance ou un Survivable Branch Server est présent sur un site pour un pool ou un serveur Standard Edition, les valeurs par défaut sont de 120 secondes pour le basculement et de 240 secondes pour le secours.

### <a name="web-services"></a>Services web

Pour modifier ou spécifier un autre paramètre pour les services web sur le serveur, modifiez ou spécifiez des paramètres dans **Services web internes** et **Services web externes**.

Dans **Services web internes**, vous pouvez spécifier les paramètres suivants :

- Si vous sélectionnez Remplacer le nom de domaine complet, vous pouvez indiquer un nom de domaine complet différent pour l’identité des services web internes sur le serveur. Par défaut, le paramètre est le nom du serveur actuel défini pour le serveur Standard Edition Server.

- Les ports d’écoute et publiés pour HTTP et HTTPS nécessaires à votre déploiement. Les paramètres par défaut, le port 80 pour le protocole HTTP et le port 443 pour le protocole HTTPS, sont les paramètres les plus courants. Ils ne doivent généralement pas être modifiés sauf si votre organisation et votre infrastructure impliquent des exigences spécifiques.

Dans **Services web externes**, vous pouvez spécifier les éléments suivants :

- Le nom de domaine complet des services web externes. Le nom de domaine complet spécifié ici sera généralement défini par les exigences de votre connexion externe, comme le proxy inverse.

- Les ports d’écoute pour HTTP et HTTPS nécessaires à votre déploiement. Les paramètres par défaut, le port 8080 pour le protocole HTTP et le port 4443 pour le protocole HTTPS, sont définis initialement. Vous pouvez modifier ces paramètres pour les ports d’écoute en fonction des exigences de votre proxy inverse et de votre réseau externe. Ces valeurs déterminent les ports d’écoute du serveur pour les demandes entrantes. Elles ne doivent généralement pas être modifiées sauf en cas de conflit entre les exigences en matière de port sur le serveur.

### <a name="mediation-server"></a>Serveur de médiation

Dans **Serveur de médiation**, vous pouvez spécifier les éléments suivants :

- Si vous colocalisez le serveur de médiation avec le serveur, activez la case à cocher **Activation de la colocalisation du serveur de médiation**. Si vous choisissez de ne pas colocaliser le serveur de médiation, cette section ne comporte aucun paramètre disponible.

- Si vous avez activé la colocalisation du serveur de médiation, vous définissez la plage de ports d’écoute du serveur pour le protocole TLS. Par défaut, il s’agit du port 5067. Si vous sélectionnez **Activer le port TCP**, vous devez définir un protocole TCP pour le serveur de médiation colocalisé. Il s’agit d’un paramètre facultatif, et vous devez consulter la configuration requise de votre passerelle ou de votre réseau public commuté pour déterminer si vous en avez besoin. Par défaut, le port TCP est le port 5068.

- Jonctions associées au serveur de médiation colocalisé. Si vous avez déjà défini des jonctions, elles pourront être associées au serveur de médiation.

- Si plusieurs passerelles sont associées à un serveur de médiation, vous pouvez spécifier une passerelle par défaut en sélectionnant la passerelle et en cliquant sur **Utiliser par défaut**. Pour désélectionner une passerelle par défaut, cliquez sur **Annuler par défaut**.

Pour plus d’informations sur la définition et la configuration des paramètres du serveur Standard Edition, reportez-vous aux rubriques [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) et [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).


