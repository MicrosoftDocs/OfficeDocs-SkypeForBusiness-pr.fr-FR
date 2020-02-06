---
title: Configuration de la prise en charge de la fédération pour un client Skype Entreprise Online
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
ms.openlocfilehash: f6b0cbb439910b97d6fcbb0fee78825b0aff9dce
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818255"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Configuration de la prise en charge de la Fédération pour un client Skype entreprise Online dans Skype entreprise Server 

Vous pouvez fournir des services de communication aux utilisateurs de votre organisation de l’une des façons suivantes :

  - Déploiement de Skype entreprise Server dans votre organisation (connu sous *le nom de services locaux*) et configuration de comptes d’utilisateurs Skype entreprise dans votre organisation.
  - Configurer un compte client Microsoft Skype entreprise Online auprès d’un fournisseur d’hébergement et configurer des comptes d’utilisateurs avec le fournisseur d’hébergement (appelé *services en ligne*).

Si vous déployez Skype entreprise dans votre organisation, vous pouvez fédérer avec les domaines d’un ou de plusieurs clients Skype entreprise online. Pour permettre la Fédération entre les utilisateurs de votre déploiement Skype entreprise et les utilisateurs Skype entreprise Online, vous devez configurer la prise en charge du client et des utilisateurs de Skype entreprise online.

> [!NOTE]  
> Cette documentation décrit uniquement les procédures de configuration de votre organisation pour la prise en charge de la Fédération avec un client Skype entreprise online. Cette documentation ne décrit pas les procédures de configuration du client Skype entreprise Online pour la prise en charge de la Fédération. 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>Conditions préalables à la Fédération avec un client Skype entreprise Online

Pour fédérer avec un client Skype entreprise Online, vous devez déjà avoir effectué le déploiement initial et la configuration de Skype entreprise Server au sein de votre organisation. Il s’agit notamment de ce qui suit :

  - Déploiement d’au moins un serveur Standard Edition Server ou un pool frontal Enterprise Edition au sein de votre organisation. 
  - Activation de comptes d’utilisateurs internes pour Skype entreprise Server. 
  - Déploiement d’au moins un serveur Edge et des autres composants nécessaires à la prise en charge de l’accès des utilisateurs externes. Pour plus d’informations, reportez-vous [à gestion de la Fédération et accès externe à Skype entreprise Server](../managing-federation-and-external-access.md).
  - Activation de la prise en charge de la Fédération au sein de votre organisation et configuration de la méthode appropriée pour contrôler l’accès par des domaines fédérés. Pour plus d’informations, reportez-vous à [activation ou désactivation de l’accès des utilisateurs à distance](../access-edge/enable-or-disable-remote-user-access.md) et à [la gestion des fournisseurs fédérés SIP pour votre organisation](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
  - Activation de l’accès des utilisateurs externes pour les utilisateurs de votre organisation. Pour plus d’informations, reportez-vous [à la rubrique affecter une stratégie d’accès utilisateur externe à un utilisateur de Skype entreprise](../external-access-policies/assign-an-external-user-access-policy.md).



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>Configurer la prise en charge de la Fédération pour un domaine Skype entreprise Online

Pour fédérer avec un client Skype entreprise Online, vous devez procéder comme suit :

  - Configurez la prise en charge du domaine du client 2010 de Skype entreprise Online (par exemple, contoso.onmicrosoft.com). Comme indiqué dans la [Configuration requise pour la Fédération avec un client Skype entreprise Online](#prerequisites-for-federating-with-a-skype-for-business-online-customer), vous devez déjà avoir activé la Fédération pour votre organisation. L’activation de la Fédération nécessite de spécifier la méthode à utiliser pour contrôler l’accès par des domaines fédérés. Si vous avez configuré votre organisation pour une utilisation de découverte, l’ajout du domaine à la liste autorisée de votre organisation est facultatif. Si vous n’avez pas activé la découverte de domaine, vous devez ajouter le nom de domaine du client Skype entreprise Online à votre liste de domaines autorisés. Vous pouvez ajouter un nom de domaine à l’aide du panneau de configuration Skype entreprise Server ou en exécutant l’applet **de commande New-CSAllowedDomain** . Pour plus d’informations sur l’utilisation du panneau de configuration Skype entreprise Server, y compris sur l’activation de la découverte des domaines, voir [gérer les fournisseurs fédérés SIP pour votre organisation dans Skype entreprise Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md). Pour plus d’informations sur l’utilisation de l’applet de nouvelle applet de **CSAllowedDomain** pour ajouter un domaine, consultez la rubrique [New-CSAllowedDomain](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAllowedDomain).

    > [!NOTE]  
    > Un client Skype entreprise online peut avoir plusieurs domaines. Si vous voulez effectuer une Fédération avec plusieurs des domaines, vous devez configurer la prise en charge de chaque domaine pour lequel vous voulez prendre en charge la Fédération et l’administrateur du client Skype entreprise Online doit activer la Fédération pour chacun des domaines Soyez fédéré.

  - Configurez la prise en charge du fournisseur d’hébergement du domaine de client Skype entreprise Online avec lequel vous souhaitez fédérer. Utilisez la procédure de cette section pour configurer la prise en charge du fournisseur d’hébergement.

    > [!NOTE]  
    > Cette étape est requise uniquement pour la Fédération avec un domaine d’un client Skype entreprise Online, et non pour la Fédération avec les domaines déployés sur site dans l’emplacement du partenaire fédéré.


### <a name="to-configure-support-for-a-hosting-provider"></a>Pour configurer la prise en charge d’un fournisseur d’hébergement

1.  À partir d’un serveur frontal, démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise Server**, puis cliquez sur **Skype entreprise Server Management Shell**.

2.  Exécutez l’applet de nouvelle applet de **CsHostingProvider** pour créer et configurer le fournisseur d’hébergement. Par exemple, exécutez :
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    L’exemple qui précède définit les paramètres suivants :
    
      - **Identity** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous êtes en train de créer. Notez que la commande échouera si un fournisseur existant a déjà été configuré avec ce paramètre Identity.
    
      - **ProxyFQDN** spécifie le nom de domaine complet du serveur proxy utilisé par le fournisseur d’hébergement. Cette valeur ne peut pas être modifiée. Si le fournisseur d’hébergement change de serveur proxy, vous devrez supprimer puis recréer l’entrée pour ce fournisseur.
    
      - **VerificationLevel** spécifie la façon dont (ou si) les messages envoyés par un fournisseur d’hébergement doivent vérifier qu’ils ont été envoyés depuis ce fournisseur.
    
      - **Enabled ** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée. Les messages ne peuvent pas être échangés entre les deux entreprises tant que cette valeur n’est pas définie sur **True **.
    
      - **EnabledSharedAddressSpace ** indique si le fournisseur d’hébergement sera utilisé dans un scénario d’espace d’adresse SIP partagé (domaine fractionné).
    
      - **HostsOCSUsers** indique si le fournisseur d’hébergement est utilisé pour héberger les comptes Skype entreprise Server. Si la valeur est **False **, le fournisseur héberge d’autres types de comptes, comme des comptes Microsoft Exchange.
    
      - **IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans votre topologie de Skype entreprise Server.
    
    Pour plus d’informations sur l’utilisation de cette cmdlet, voir [New-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider).

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>Configurer l’accès utilisateur pour la Fédération avec un client Skype entreprise Online 

Vous devez configurer les comptes d’utilisateurs de tous les utilisateurs de votre organisation pour qu’ils puissent communiquer avec des partenaires fédérés. Cette configuration est appliquée à tous les partenaires fédérés, y compris aux domaines de clients Microsoft Skype entreprise Online avec lesquels vous prenez en charge la Fédération. Pour plus d’informations sur la configuration de la prise en charge de la Fédération pour les comptes d’utilisateurs, reportez-vous à la rubrique [configuration de stratégies pour contrôler l’accès des utilisateurs fédérés](../external-access-policies/configure-policies-to-control-federated-user-access.md) et [attribuer une stratégie d’accès utilisateur externe à un utilisateur de Skype entreprise](../external-access-policies/assign-an-external-user-access-policy.md)

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Vérification des communications avec un client Skype entreprise Online dans Skype entreprise Server

Pour permettre aux utilisateurs Skype entreprise de votre organisation de communiquer avec des utilisateurs d’un client Skype entreprise Online, vous devez effectuer les étapes suivantes :

  - Rempli toutes les conditions préalables. Cela inclut le déploiement de vos serveurs internes et de périphérie, l’activation de la prise en charge de la Fédération pour votre organisation et la configuration des comptes d’utilisateurs. Pour plus d’informations, reportez-vous [à la configuration requise pour la Fédération avec un client Skype entreprise Online](#prerequisites-for-federating-with-a-skype-for-business-online-customer).
  - Configuration de la prise en charge de l’accès au domaine dans votre déploiement interne. Cela inclut la création d’une entrée de fournisseur d’hébergement et la configuration de votre déploiement pour autoriser l’accès à partir du domaine du client de Skype entreprise online. Pour plus d’informations, consultez [la rubrique Configurer la prise en charge de la Fédération pour un domaine Skype entreprise Online](#configure-federation-support-for-a-skype-for-business-online-domain).
  - Configuré vos comptes d’utilisateurs pour la prise en charge de la Fédération ; Pour plus d’informations, reportez-vous à [la rubrique Configuration de l’accès utilisateur pour la Fédération avec un client Skype entreprise Online](#configure-user-access-for-federation-with-a-skype-for-business-online-customer).

Après avoir effectué toutes les étapes décrites dans le tableau ci-dessous, l’administrateur de Skype entreprise Online dispose de toutes les informations de configuration de ses services en ligne pour la prise en charge de la Fédération avec votre organisation. un utilisateur interne au sein de votre organisation et un utilisateur du client Skype entreprise online. Si la communication échoue, utilisez l’outil de journalisation de votre serveur de périphérie pour capturer les fichiers de journaux et de suivi afin de résoudre le problème. 
