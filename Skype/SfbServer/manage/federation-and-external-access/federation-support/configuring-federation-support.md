---
title: Configuration de prise en charge de la fédération pour un Skype pour les clients professionnels en ligne
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Si vous déployez Skype pour les entreprises dans votre organisation, vous pouvez vous fédérer avec les domaines d’un ou plusieurs Skype pour les clients professionnels en ligne. '
ms.openlocfilehash: 978da18a4ae639e52dedd6971c1a2291c94cb9f1
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223366"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Configuration de prise en charge de la fédération pour un Skype pour client Business Online dans Skype pour Business Server 

Vous pouvez fournir des services de communication aux utilisateurs de votre organisation dans une des manières suivantes :

  - Déploiement Skype pour Business Server dans votre organisation (également appelé en tant que *services sur site*) et le paramétrage de Skype pour les comptes d’utilisateurs professionnels de votre organisation.
  - Configuration d’un Skype Microsoft Business Online compte client avec un fournisseur d’hébergement et la configuration de comptes d’utilisateurs avec le fournisseur d’hébergement (également appelé prestataire de *services en ligne*).

Si vous déployez Skype pour les entreprises dans votre organisation, vous pouvez vous fédérer avec les domaines d’un ou plusieurs Skype pour les clients professionnels en ligne. Pour activer la fédération entre les utilisateurs de votre Skype sur site pour le déploiement d’entreprise et d’un Skype pour les clients professionnels en ligne, vous devez configurer la prise en charge pour le domaine et les utilisateurs de la Skype pour les clients professionnels en ligne.

> [!NOTE]  
> Cette documentation décrit uniquement les procédures de configuration de votre organisation pour prendre en charge la fédération avec un Skype pour les clients professionnels en ligne. Cette documentation ne décrit pas les procédures de configuration de la Skype pour client Business en ligne prendre en charge la fédération. 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>Conditions requises pour la fédération avec un Skype pour les clients professionnels en ligne

Pour établir une fédération avec un Skype pour les clients professionnels en ligne, vous devez avoir déjà effectué le déploiement initial et configuration de Skype pour Business Server dans votre organisation. Il s’agit notamment de ce qui suit :

  - Déploiement d’au moins un serveur Standard Edition server ou un pool frontal Enterprise Edition dans votre organisation. 
  - Activation des comptes d’utilisateurs internes pour Skype pour Business Server. 
  - Déploiement d’au moins un serveur de périphérie et les autres composants requis pour prendre en charge l’accès des utilisateurs externes. Pour plus d’informations, voir [Managing fédération et accès externe aux Skype pour Business Server](../managing-federation-and-external-access.md).
  - Prise en charge de la fédération dans votre organisation et la configuration de la méthode appropriée pour contrôler l’accès à des domaines fédérés. Pour plus d’informations, voir [Activer ou désactiver l’accès des utilisateurs distants](../access-edge/enable-or-disable-remote-user-access.md) et [Manage SIP federated fournisseurs pour votre organisation](../sip-providers/manage-sip-federated-providers-for-your-organization.md).
  - Activer l’accès des utilisateurs externes pour les utilisateurs de votre organisation. Pour plus d’informations, voir [attribuer une stratégie d’accès utilisateur externe à un Skype pour un utilisateur activé Business](../external-access-policies/assign-an-external-user-access-policy.md).



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>Configurer la prise en charge de la fédération pour un Skype pour le domaine d’entreprise en ligne

Fédération avec un Skype pour les clients professionnels en ligne, vous devez effectuer les étapes suivantes :

  - Configurer la prise en charge pour le domaine de la Skype pour le client de petite entreprise 2010 en ligne (par exemple, contoso.onmicrosoft.com). Comme spécifié dans les [conditions requises pour la fédération avec un Skype pour les clients professionnels en ligne](#prerequisites-for-federating-with-a-skype-for-business-online-customer), vous devez ont déjà activé la fédération pour votre organisation. Activation de la fédération requiert la spécification de la méthode à utiliser pour contrôler l’accès à des domaines fédérés. Si vous avez configuré votre organisation pour utiliser la détection, l’ajout du domaine à la liste autorisée de votre organisation est facultative. Si vous n’avez pas activé la découverte des domaines, vous devez ajouter le nom de domaine de la Skype pour client Business Online à votre liste des domaines autorisés. Vous pouvez ajouter un nom de domaine à l’aide de Skype pour le panneau de configuration serveur Business ou en exécutant l’applet de commande **New-CSAllowedDomain** . Pour plus d’informations sur l’utilisation de Skype pour Business Server le panneau de configuration, y compris l’activation de la découverte des domaines, voir [Gérer SIP federated providers pour votre organisation dans Skype pour Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md). Pour plus d’informations sur l’utilisation de l’applet de commande **New-CSAllowedDomain** pour ajouter un domaine, voir [New-CsAllowedDomain](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAllowedDomain).

    > [!NOTE]  
    > Un Skype pour les clients professionnels en ligne peut avoir plusieurs domaines. Si vous voulez vous fédérer avec plusieurs domaines, vous devez configurer la prise en charge pour chaque domaine individuel avec lequel vous souhaitez prendre en charge de la fédération et l’administrateur de la Skype pour client Business Online doit activer la fédération pour chacun des domaines à être fédérés.

  - Configurer la prise en charge pour le fournisseur d’hébergement de le Skype pour Business Online domaine client avec laquelle vous voulez vous fédérer. Utilisez la procédure de cette section pour configurer la prise en charge pour le fournisseur d’hébergement.

    > [!NOTE]  
    > Cette étape est requise uniquement pour la fédération avec un domaine d’un Skype pour les clients professionnels en ligne, et non pour la fédération avec n’importe quel domaine qui est déployé sur site à l’emplacement d’un partenaire fédéré.


### <a name="to-configure-support-for-a-hosting-provider"></a>Pour configurer la prise en charge pour un fournisseur d’hébergement

1.  À partir d’un serveur frontal, démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server**, puis cliquez sur **Skype pour Business Server Management Shell**.

2.  Exécutez l’applet de commande **New-CsHostingProvider** pour créer et configurer le fournisseur d’hébergement. Par exemple, exécutez :
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    L’exemple qui précède définit les paramètres suivants :
    
      - **Identité** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez. Notez que la commande échouera si un fournisseur existant a déjà été configuré avec ce paramètre Identity.
    
      - **ProxyFQDN** Spécifie le nom de domaine complet (FQDN) du serveur proxy utilisé par le fournisseur d’hébergement. Cette valeur ne peut pas être modifiée. Si le fournisseur d’hébergement change de serveur proxy, vous devrez supprimer puis recréer l’entrée pour ce fournisseur.
    
      - **VerificationLevel** spécifie comment (ou si) les messages envoyés à partir d’un fournisseur d’hébergement sont vérifiés pour s’assurer qu’ils ont été envoyés par ce fournisseur.
    
      - **Enabled ** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée. Les messages ne peuvent pas être échangés entre les deux entreprises tant que cette valeur n’est pas définie sur **True **.
    
      - **EnabledSharedAddressSpace ** indique si le fournisseur d’hébergement sera utilisé dans un scénario d’espace d’adresse SIP partagé (domaine fractionné).
    
      - **HostsOCSUsers** indique si le fournisseur d’hébergement est utilisé pour héberger Skype pour les comptes Business Server. Si la valeur est **False **, le fournisseur héberge d’autres types de comptes, comme des comptes Microsoft Exchange.
    
      - **IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans votre Skype pour la topologie du serveur d’entreprise.
    
    Pour plus d’informations sur l’utilisation de cette applet de commande, voir [New-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider).

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>Configurer l’accès des utilisateurs pour la fédération avec un Skype pour les clients professionnels en ligne 

Vous devez configurer l’utilisateur de tous les utilisateurs de votre organisation afin que les comptes d’être autorisé à communiquer avec les partenaires fédérés. Cette configuration est appliquée pour tous les partenaires fédérés, y compris tout Skype Microsoft pour les domaines client Business en ligne avec lequel vous prenez en charge la fédération. Pour plus d’informations sur la configuration de la prise en charge de la fédération pour les comptes d’utilisateur, consultez [configurer les stratégies de contrôle des accès des utilisateurs fédérés](../external-access-policies/configure-policies-to-control-federated-user-access.md) et [affecter une stratégie d’accès utilisateur externe à un Skype pour un utilisateur activé Business](../external-access-policies/assign-an-external-user-access-policy.md).

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Vérifier les communications avec un Skype pour client Business Online dans Skype pour Business Server

Pour activer Skype pour les utilisateurs professionnels de votre organisation de communiquer avec les utilisateurs d’un Skype pour les clients professionnels en ligne, vous devez avoir exécuté les étapes suivantes :

  - Remplies tous les éléments prérequis. Cela inclut le déploiement interne et prendre en charge des serveurs de périphérie, activation de la fédération pour votre organisation, ainsi que des comptes d’utilisateur. Pour plus d’informations, voir [conditions requises pour la fédération avec un Skype pour les clients professionnels en ligne](#prerequisites-for-federating-with-a-skype-for-business-online-customer).
  - Prise en charge des accès de domaine configuré dans votre déploiement interne. Cela inclut la création d’une entrée d’hôte fournisseur et configuration de votre déploiement pour autoriser l’accès à partir de la Skype pour le domaine d’entreprise en ligne du client. Pour plus d’informations, consultez [configurer la fédération prise en charge pour un Skype pour le domaine d’entreprise en ligne](#configure-federation-support-for-a-skype-for-business-online-domain).
  - Configuré vos comptes d’utilisateurs pour prendre en charge la fédération. Pour plus d’informations, voir [configurer l’accès des utilisateurs pour la fédération avec un Skype pour les clients professionnels en ligne](#configure-user-access-for-federation-with-a-skype-for-business-online-customer).

Après avoir effectué toutes ces étapes, l’administrateur de la Skype pour toute la configuration des services en ligne pour prendre en charge la fédération avec votre organisation effectue Business en ligne, vérifier les communications en testant les communications entre un utilisateur interne dans votre organisation et un utilisateur de la Skype pour les clients professionnels en ligne. Si la communication ne fonctionne pas, utilisez l’outil de journalisation à partir de votre serveur Edge pour capturer les fichiers journaux et de suivi afin de résoudre le problème. 