---
title: 'Lync Server 2013 : configurer la prise en charge de la Fédération pour un domaine Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation support for a Lync Online domain
ms:assetid: 19d5d5be-cd7f-47b8-b6c5-651a3191def7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202166(v=OCS.15)
ms:contentKeyID: 48183530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f883e8d730e63788b4cbe0ccd3315f21e6fea97
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726594"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a>Configurer la prise en charge de la Fédération pour un domaine Lync Online dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Pour fédérer avec un client Microsoft Lync Online 2010, vous devez effectuer les étapes suivantes :

  - Configurer la prise en charge du domaine du client 2010 Lync Online (par exemple, contoso.onmicrosoft.com). Comme indiqué dans la section [Configuration requise pour la Fédération avec un client Lync Online dans Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) de cette documentation, vous devez déjà avoir activé la Fédération pour votre organisation. L’activation de la Fédération nécessite de spécifier la méthode à utiliser pour contrôler l’accès par des domaines fédérés. Si vous avez configuré votre organisation pour une utilisation de découverte, l’ajout du domaine à la liste autorisée de votre organisation est facultatif. Si vous n’avez pas activé la découverte de domaine, vous devez ajouter le nom de domaine du client Lync Online à votre liste de domaines autorisés. Vous pouvez ajouter un nom de domaine à l’aide du panneau de configuration de Lync Server ou en exécutant l’applet **de commande New-CSAllowedDomain** . Pour plus d’informations sur l’utilisation du panneau de configuration de Lync Server, y compris sur l’activation de la découverte des domaines, voir [gérer les fournisseurs fédérés SIP pour votre organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) dans la documentation des opérations. Pour plus d’informations sur l’utilisation de l’applet de nouvelle applet de **CSAllowedDomain** pour ajouter un domaine, consultez la rubrique [New-CSAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) dans la documentation opérations.
    
    <div>
    

    > [!NOTE]  
    > Un client Lync Online peut avoir plusieurs domaines. Si vous voulez effectuer une Fédération avec plusieurs des domaines, vous devez configurer la prise en charge de chaque domaine pour lequel vous voulez prendre en charge la Fédération, et l’administrateur du client Lync Online doit activer la Fédération pour chacun des domaines à fédérer.

    
    </div>

  - Configurez la prise en charge du fournisseur d’hébergement du domaine du client 2010 Lync Online avec lequel vous voulez fédérer. Utilisez la procédure de cette section pour configurer la prise en charge du fournisseur d’hébergement.
    
    <div>
    

    > [!NOTE]  
    > Cette étape est requise uniquement pour la Fédération avec un domaine d’un client Lync Online, et non pour la Fédération avec tout domaine déployé sur site dans l’emplacement du partenaire fédéré.

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a>Pour configurer la prise en charge d’un fournisseur d’hébergement

1.  À partir d’un serveur frontal, démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de nouvelle applet de **CsHostingProvider** pour créer et configurer le fournisseur d’hébergement. Par exemple, exécutez :
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    L’exemple qui précède définit les paramètres suivants :
    
      - **Identity** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous êtes en train de créer. Notez que la commande échouera si un fournisseur existant a déjà été configuré avec ce paramètre Identity.
    
      - **ProxyFQDN** spécifie le nom de domaine complet du serveur proxy utilisé par le fournisseur d’hébergement. Cette valeur ne peut pas être modifiée. Si le fournisseur d’hébergement change de serveur proxy, vous devrez supprimer puis recréer l’entrée pour ce fournisseur.
    
      - **VerificationLevel** spécifie la façon dont (ou si) les messages envoyés par un fournisseur d’hébergement doivent vérifier qu’ils ont été envoyés depuis ce fournisseur.
    
      - **Enabled ** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée. Les messages ne peuvent pas être échangés entre les deux entreprises tant que cette valeur n’est pas définie sur **True **.
    
      - **EnabledSharedAddressSpace ** indique si le fournisseur d’hébergement sera utilisé dans un scénario d’espace d’adresse SIP partagé (domaine fractionné).
    
      - **HostsOCSUsers** indique si le fournisseur d’hébergement est utilisé pour héberger des comptes Lync Server. Si la valeur est **False **, le fournisseur héberge d’autres types de comptes, comme des comptes Microsoft Exchange.
    
      - **IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans la topologie de votre serveur Lync.
    
    Pour plus d’informations sur l’utilisation de cette applet de connexion, voir [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) dans la documentation sur les opérations.

</div>

</div>

<span> </span>

</div>

</div>

</div>

