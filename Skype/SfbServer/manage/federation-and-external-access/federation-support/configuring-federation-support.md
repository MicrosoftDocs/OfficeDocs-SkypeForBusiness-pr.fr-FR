---
title: Configuration de la prise en charge de la Fédération pour un client Skype entreprise Online
ms.reviewer: ''
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Si vous déployez Skype entreprise dans votre organisation, vous pouvez fédérer avec les domaines d’un ou de plusieurs clients Skype entreprise online. '
ms.openlocfilehash: b7488d21463782a978c9a3d6263d9fdfc2e59dd9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037284"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Configuration de la prise en charge de la Fédération pour un client Skype entreprise Online dans Skype entreprise Server 

Vous pouvez fournir des services de communication aux utilisateurs de votre organisation de l’une des façons suivantes :

  - Le déploiement de Skype entreprise Server dans votre organisation (appelés *services locaux*) et la configuration des comptes d’utilisateur Skype entreprise dans votre organisation.
  - La configuration d’un compte de client Microsoft Skype entreprise Online avec un fournisseur d’hébergement et la configuration des comptes d’utilisateurs avec le fournisseur d’hébergement (appelés *services en ligne*).

Si vous déployez Skype entreprise dans votre organisation, vous pouvez fédérer avec les domaines d’un ou de plusieurs clients Skype entreprise online. Pour activer la Fédération entre les utilisateurs de votre déploiement Skype entreprise local et les utilisateurs d’un client Skype entreprise Online, vous devez configurer la prise en charge du domaine et des utilisateurs du client Skype entreprise online.

> [!NOTE]  
> Cette documentation décrit uniquement les procédures de configuration de votre organisation pour la prise en charge de la Fédération avec un client Skype entreprise online. Cette documentation ne décrit pas les procédures de configuration du client Skype entreprise Online pour la prise en charge de la Fédération. 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>Conditions préalables à la Fédération avec un client Skype entreprise Online

Pour fédérer avec un client Skype entreprise Online, vous devez avoir déjà effectué le déploiement initial et la configuration de Skype entreprise Server dans votre organisation. Les voici :

  - Le déploiement d’au moins un serveur Standard Edition Server ou d’un pool frontal Enterprise Edition dans votre organisation. 
  - Activation des comptes d’utilisateur internes pour Skype entreprise Server. 
  - Le déploiement d’au moins un serveur Edge et des autres composants requis pour prendre en charge l’accès des utilisateurs externes. Pour plus d’informations, reportez-vous à la rubrique gestion de la [Fédération et de l’accès externe à Skype entreprise Server](../managing-federation-and-external-access.md).
  - Activation de la prise en charge de la Fédération au sein de votre organisation et configuration de la méthode appropriée pour contrôler l’accès par les domaines fédérés. Pour plus d’informations, consultez la rubrique [activation ou désactivation de l’accès des utilisateurs distants](../access-edge/enable-or-disable-remote-user-access.md) et [gestion des fournisseurs fédérés SIP pour votre organisation](../sip-providers/manage-sip-federated-providers-for-your-organization.md).
  - Activation de l’accès des utilisateurs externes pour les utilisateurs de votre organisation. Pour plus d’informations, consultez [la rubrique attribuer une stratégie d’accès des utilisateurs externes à un utilisateur prenant en charge Skype entreprise](../external-access-policies/assign-an-external-user-access-policy.md).



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>Configurer la prise en charge de la Fédération pour un domaine Skype entreprise Online

Pour fédérer avec un client Skype entreprise Online, vous devez effectuer les étapes suivantes :

  - Configurez la prise en charge du domaine du client Skype entreprise Online 2010 (par exemple, contoso.onmicrosoft.com). Comme indiqué dans la [Configuration requise pour la Fédération avec un client Skype entreprise Online](#prerequisites-for-federating-with-a-skype-for-business-online-customer), vous devez avoir déjà activé la Fédération pour votre organisation. L’activation de la Fédération nécessite de spécifier la méthode à utiliser pour contrôler l’accès par les domaines fédérés. Si vous avez configuré votre organisation pour utiliser la découverte, l’ajout du domaine à la liste autorisée de votre organisation est facultatif. Si vous n’avez pas activé la découverte de domaine, vous devez ajouter le nom de domaine du client Skype entreprise Online à votre liste de domaines autorisés. Vous pouvez ajouter un nom de domaine à l’aide du panneau de configuration de Skype entreprise Server ou en exécutant la cmdlet **New-CSAllowedDomain** . Pour plus d’informations sur l’utilisation du panneau de configuration de Skype entreprise Server, notamment sur l’activation de la découverte de domaines, voir [gérer les fournisseurs fédérés SIP pour votre organisation dans Skype entreprise Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md). Pour plus d’informations sur l’utilisation de la cmdlet **New-CSAllowedDomain** pour ajouter un domaine, voir [New-CSAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain).

    > [!NOTE]  
    > Un client Skype entreprise online peut avoir plusieurs domaines. Si vous souhaitez fédérer avec plusieurs domaines, vous devez configurer la prise en charge pour chaque domaine individuel avec lequel vous souhaitez prendre en charge la Fédération, et l’administrateur du client Skype entreprise Online doit activer la Fédération pour chacun des domaines pour être fédéré.

  - Configurez la prise en charge du fournisseur d’hébergement du domaine de client Skype entreprise Online avec lequel vous souhaitez vous fédérer. Utilisez la procédure décrite dans cette section pour configurer la prise en charge du fournisseur d’hébergement.

    > [!NOTE]  
    > Cette étape est requise uniquement pour la Fédération avec un domaine d’un client Skype entreprise Online, pas pour la Fédération avec un domaine déployé sur site sur un emplacement de partenaire fédéré.


### <a name="to-configure-support-for-a-hosting-provider"></a>Pour configurer la prise en charge d’un fournisseur d’hébergement

1.  À partir d’un serveur frontal, démarrez Skype entreprise Server Management Shell : cliquez successivement sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server**, puis sur **Skype entreprise Server Management Shell**.

2.  Exécutez la cmdlet **New-CsHostingProvider** pour créer et configurer le fournisseur d’hébergement. Par exemple, exécutez :
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    L’exemple qui précède définit les paramètres suivants :
    
      - **Identity** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez. Notez que la commande échoue si un fournisseur existant a déjà été configuré avec cette identité.
    
      - **ProxyFQDN** spécifie le nom de domaine complet du serveur proxy utilisé par le fournisseur d’hébergement. Cette valeur ne peut pas être modifiée. Si le fournisseur d’hébergement modifie son serveur proxy, vous devrez supprimer, puis recréer l’entrée pour ce fournisseur.
    
      - **VerificationLevel** spécifie comment (ou si) les messages envoyés à partir d’un fournisseur d’hébergement sont vérifiés pour s’assurer qu’ils ont été envoyés à partir de ce fournisseur.
    
      - **Enabled** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée. Les messages ne peuvent pas être échangés entre les deux organisations tant que cette valeur n’est pas définie sur **true**.
    
      - **EnabledSharedAddressSpace** indique si le fournisseur d’hébergement est utilisé dans un scénario d’espace d’adressage SIP partagé (domaine fractionné).
    
      - **HostsOCSUsers** indique si le fournisseur d’hébergement est utilisé pour héberger les comptes Skype entreprise Server. Si la **valeur est false**, le fournisseur héberge d’autres types de comptes, tels que les comptes Microsoft Exchange.
    
      - **IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans votre topologie Skype entreprise Server.
    
    Pour plus d’informations sur l’utilisation de cette cmdlet, consultez la rubrique [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider).

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>Configurer l’accès utilisateur pour la Fédération avec un client Skype entreprise Online 

Vous devez configurer les comptes de tous les utilisateurs de votre organisation pour qu’ils puissent communiquer avec des partenaires fédérés. Cette configuration est appliquée pour tous les partenaires fédérés, y compris les domaines de client Microsoft Skype entreprise Online avec lesquels vous prenez en charge la Fédération. Pour plus d’informations sur la configuration de la prise en charge de la Fédération pour les comptes d’utilisateur, consultez la rubrique [configure Policies to Control Federated User Access](../external-access-policies/configure-policies-to-control-federated-user-access.md) et [assignez une stratégie d’accès des utilisateurs externes à un utilisateur prenant en charge Skype entreprise](../external-access-policies/assign-an-external-user-access-policy.md).

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Vérifier les communications avec un client Skype entreprise Online dans Skype entreprise Server

Pour permettre aux utilisateurs Skype entreprise de votre organisation de communiquer avec les utilisateurs d’un client Skype entreprise Online, vous devez avoir effectué les étapes suivantes :

  - Respectez tous les éléments prérequis. Cela inclut le déploiement de vos serveurs internes et de périphérie, l’activation de la prise en charge de la Fédération pour votre organisation et la configuration des comptes d’utilisateurs. Pour plus d’informations, reportez-vous à [la rubrique conditions préalables pour la Fédération avec un client Skype entreprise Online](#prerequisites-for-federating-with-a-skype-for-business-online-customer).
  - Vous avez configuré la prise en charge de l’accès au domaine dans votre déploiement interne. Cela inclut la création d’une entrée de fournisseur d’hôte et la configuration de votre déploiement pour autoriser l’accès à partir du domaine du client Skype entreprise online. Pour plus d’informations, consultez [la rubrique Configurer la prise en charge de la Fédération pour un domaine Skype entreprise Online](#configure-federation-support-for-a-skype-for-business-online-domain).
  - Vous avez configuré les comptes de vos utilisateurs de sorte qu’ils prennent en charge la fédération. Pour plus d’informations, voir [configurer l’accès utilisateur pour la Fédération avec un client Skype entreprise Online](#configure-user-access-for-federation-with-a-skype-for-business-online-customer).

Une fois que vous avez effectué toutes ces étapes et que l’administrateur du client Skype entreprise Online termine la configuration de ses services en ligne pour prendre en charge la Fédération avec votre organisation, vérifiez les communications en testant les communications entre un utilisateur interne dans votre organisation et un utilisateur du client Skype entreprise online. Si la communication échoue, utilisez l’outil de journalisation à partir de votre serveur Edge pour capturer les fichiers journaux et de suivi afin de résoudre le problème. 
