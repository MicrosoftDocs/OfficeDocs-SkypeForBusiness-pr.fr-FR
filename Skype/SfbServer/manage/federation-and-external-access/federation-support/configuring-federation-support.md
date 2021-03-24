---
title: Configuration de la prise en charge de la fédération pour un client Skype Entreprise Online
ms.reviewer: ''
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Si vous déployez Skype Entreprise dans votre organisation, vous pouvez vous fédérer avec les domaines d’un ou plusieurs clients Skype Entreprise Online. '
ms.openlocfilehash: c241af4700662c11366a71a55afad28ed3f8b7db
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098950"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Configuration de la prise en charge de la fédération pour un client Skype Entreprise Online dans Skype Entreprise Server 

Vous pouvez fournir des services de communication aux utilisateurs de votre organisation de l’une des façons suivantes :

  - Déploiement de Skype Entreprise Server dans votre organisation *(appelés services* locaux) et configuration de comptes d’utilisateur Skype Entreprise dans votre organisation.
  - Configuration d’un compte client Microsoft Skype Entreprise Online avec un fournisseur d’hébergement et configuration de comptes d’utilisateurs avec le fournisseur d’hébergement *(appelés services en ligne).*

Si vous déployez Skype Entreprise dans votre organisation, vous pouvez fédérer avec les domaines d’un ou plusieurs clients Skype Entreprise Online. Pour activer la fédération entre les utilisateurs de votre déploiement Skype Entreprise local et les utilisateurs d’un client Skype Entreprise Online, vous devez configurer la prise en charge du domaine et des utilisateurs du client Skype Entreprise Online.

> [!NOTE]  
> Cette documentation décrit uniquement les procédures de configuration de votre organisation pour prendre en charge la fédération avec un client Skype Entreprise Online. Cette documentation ne décrit pas les procédures de configuration du client Skype Entreprise Online pour prendre en charge la fédération. 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>Conditions préalables à la fédération avec un client Skype Entreprise Online

Pour vous fédérer avec un client Skype Entreprise Online, vous devez avoir déjà effectué le déploiement initial et la configuration de Skype Entreprise Server dans votre organisation. Les voici :

  - Déploiement d’au moins un serveur Standard Edition server ou d’un pool frontal Enterprise Edition dans votre organisation. 
  - Activation des comptes d’utilisateurs internes pour Skype Entreprise Server. 
  - Déploiement d’au moins un serveur Edge et des autres composants requis pour prendre en charge l’accès des utilisateurs externes. Pour plus d’informations, voir [Gestion de la fédération et de l’accès externe à Skype Entreprise Server.](../managing-federation-and-external-access.md)
  - Activation de la prise en charge de la fédération au sein de votre organisation et configuration de la méthode appropriée pour contrôler l’accès par domaines fédérés. Pour plus d’informations, voir Activer ou désactiver [l’accès](../access-edge/enable-or-disable-remote-user-access.md) des utilisateurs distants et Gérer les fournisseurs [fédérés SIP pour votre organisation.](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
  - Activation de l’accès des utilisateurs externes pour les utilisateurs de votre organisation. Pour plus d’informations, voir Affecter une stratégie d’accès des utilisateurs externes [à un utilisateur activé pour Skype Entreprise.](../external-access-policies/assign-an-external-user-access-policy.md)



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>Configurer la prise en charge de la fédération pour un domaine Skype Entreprise Online

Pour vous fédéré avec un client Skype Entreprise Online, vous devez effectuer les étapes suivantes :

  - Configurer la prise en charge du domaine du client Skype Entreprise Online 2010 (par exemple, contoso.onmicrosoft.com). Comme indiqué dans les [conditions préalables](#prerequisites-for-federating-with-a-skype-for-business-online-customer)à la fédération avec un client Skype Entreprise Online, vous devez avoir déjà activé la fédération pour votre organisation. L’activation de la fédération nécessite de spécifier la méthode à utiliser pour contrôler l’accès par les domaines fédérés. Si vous avez configuré votre organisation pour utiliser la découverte, l’ajout du domaine à la liste autorisée de votre organisation est facultatif. Si vous n’avez pas activé la découverte de domaine, vous devez ajouter le nom de domaine du client Skype Entreprise Online à votre liste des domaines autorisés. Vous pouvez ajouter un nom de domaine à l’aide du Panneau de contrôle Skype Entreprise Server ou en exécutant l’cmdlet **New-CSAllowedDomain.** Pour plus d’informations sur l’utilisation du Panneau de contrôle Skype Entreprise Server, y compris l’activation de la découverte de domaines, voir Gérer les fournisseurs fédérés SIP pour votre organisation [dans Skype Entreprise Server.](../sip-providers/manage-sip-federated-providers-for-your-organization.md) Pour plus d’informations sur l’utilisation de l’cmdlet **New-CSAllowedDomain** pour ajouter un domaine, voir [New-CsAllowedDomain](/powershell/module/skype/New-CsAllowedDomain).

    > [!NOTE]  
    > Un client Skype Entreprise Online peut avoir plusieurs domaines. Si vous souhaitez vous fédérer avec plusieurs domaines, vous devez configurer la prise en charge de chaque domaine avec lequel vous souhaitez prendre en charge la fédération, et l’administrateur du client Skype Entreprise Online doit activer la fédération pour chacun des domaines à fédérer.

  - Configurez la prise en charge du fournisseur d’hébergement du domaine client Skype Entreprise Online avec lequel vous souhaitez vous fédérer. Utilisez la procédure de cette section pour configurer la prise en charge du fournisseur d’hébergement.

    > [!NOTE]  
    > Cette étape est requise uniquement pour la fédération avec un domaine d’un client Skype Entreprise Online, et non pour la fédération avec un domaine déployé en local à l’emplacement d’un partenaire fédéré.


### <a name="to-configure-support-for-a-hosting-provider"></a>Pour configurer la prise en charge d’un fournisseur d’hébergement

1.  À partir d’un serveur frontal, démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **Server,** puis sur Skype Entreprise **Server Management Shell.**

2.  Exécutez **l’cmdlet New-CsHostingProvider** pour créer et configurer le fournisseur d’hébergement. Par exemple, exécutez :
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    L’exemple qui précède définit les paramètres suivants :
    
      - **Identity** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez. Notez que la commande échouera si un fournisseur existant a déjà été configuré avec cette identité.
    
      - **ProxyFQDN** spécifie le nom de domaine complet du serveur proxy utilisé par le fournisseur d’hébergement. Cette valeur ne peut pas être modifiée. Si le fournisseur d’hébergement modifie son serveur proxy, vous devrez supprimer, puis recréer l’entrée pour ce fournisseur.
    
      - **VerificationLevel spécifie** comment (ou si) les messages envoyés par un fournisseur d’hébergement sont vérifiés pour s’assurer qu’ils ont été envoyés à partir de ce fournisseur.
    
      - **Enabled** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée. Les messages ne peuvent pas être échangés entre les deux organisations tant que cette valeur n’est pas définie sur **True**.
    
      - **EnabledSharedAddressSpace** indique si le fournisseur d’hébergement est utilisé dans un scénario d’espace d’adressace SIP partagé (domaine partagé).
    
      - **HostsOCSUsers indique** si le fournisseur d’hébergement est utilisé pour héberger des comptes Skype Entreprise Server. Si **la false**, le fournisseur héberge d’autres types de comptes, tels que les comptes Microsoft Exchange.
    
      - **IsLocal indique** si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans votre topologie Skype Entreprise Server.
    
    Pour plus d’informations sur l’utilisation de cette cmdlet, voir [New-CsHostingProvider](/powershell/module/skype/New-CsHostingProvider).

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>Configurer l’accès des utilisateurs pour la fédération avec un client Skype Entreprise Online 

Vous devez configurer les comptes de tous les utilisateurs de votre organisation pour qu’ils puissent communiquer avec des partenaires fédérés. Cette configuration est appliquée à tous les partenaires fédérés, y compris les domaines clients Microsoft Skype Entreprise Online avec lesquels vous prisez en charge la fédération. Pour plus d’informations sur la configuration [](../external-access-policies/configure-policies-to-control-federated-user-access.md) de la prise en charge de la fédération pour les comptes d’utilisateurs, voir Configurer des stratégies pour contrôler l’accès des utilisateurs fédérés et Affecter une stratégie d’accès des utilisateurs externes à un utilisateur activé pour [Skype Entreprise.](../external-access-policies/assign-an-external-user-access-policy.md)

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Vérifier les communications avec un client Skype Entreprise Online dans Skype Entreprise Server

Pour permettre aux utilisateurs Skype Entreprise de votre organisation de communiquer avec les utilisateurs d’un client Skype Entreprise Online, vous devez avoir effectué les étapes suivantes :

  - Toutes les conditions préalables sont remplies. Cela inclut le déploiement de vos serveurs internes et edge, l’activation de la prise en charge de la fédération pour votre organisation et la configuration des comptes d’utilisateurs. Pour plus d’informations, [voir Conditions préalables à la fédération avec un client Skype Entreprise Online.](#prerequisites-for-federating-with-a-skype-for-business-online-customer)
  - Vous avez configuré la prise en charge de l’accès au domaine dans votre déploiement interne. Cela inclut la création d’une entrée de fournisseur d’hôtes et la configuration de votre déploiement pour autoriser l’accès à partir du domaine du client Skype Entreprise Online. Pour plus d’informations, voir [Configurer la prise en charge de la fédération pour un domaine Skype Entreprise Online.](#configure-federation-support-for-a-skype-for-business-online-domain)
  - Vous avez configuré les comptes de vos utilisateurs de sorte qu’ils prennent en charge la fédération. Pour plus d’informations, voir [Configurer l’accès des utilisateurs pour la fédération avec un client Skype Entreprise Online.](#configure-user-access-for-federation-with-a-skype-for-business-online-customer)

Une fois que vous avez effectué toutes ces étapes et que l’administrateur du client Skype Entreprise Online a terminé la configuration de ses services en ligne pour prendre en charge la fédération avec votre organisation, vérifiez les communications en testant les communications entre un utilisateur interne de votre organisation et un utilisateur du client Skype Entreprise Online. Si la communication ne réussit pas, utilisez l’outil de journalisation de votre serveur Edge pour capturer les fichiers journaux et de suivi afin de résoudre le problème.