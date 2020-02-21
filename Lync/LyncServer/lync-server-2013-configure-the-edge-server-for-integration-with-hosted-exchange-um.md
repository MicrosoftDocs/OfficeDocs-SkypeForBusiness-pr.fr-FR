---
title: Configuration du serveur Edge pour l’intégration à la messagerie unifiée Exchange hébergée
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Edge Server for integration with hosted Exchange UM
ms:assetid: ede3f2f9-f412-418e-a705-8d8ec98176c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399075(v=OCS.15)
ms:contentKeyID: 48185745
ms.date: 01/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: def07f8caf302471e2d1466bb1a783732ebdc691
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-edge-server-for-integration-with-hosted-exchange-um"></a>Configuration du serveur Edge pour l’intégration à la messagerie unifiée Exchange hébergée

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-01-23_

Pour fournir à vos utilisateurs Lync Server 2013 des fonctionnalités de messagerie vocale sur la messagerie unifiée Exchange hébergée, vous devez effectuer les tâches de configuration suivantes sur le serveur Edge :

  - Configurez le serveur Edge pour la fédération.

  - Répliquez les données du magasin central de gestion sur le serveur Edge et vérifiez la réplication.

  - Créez un fournisseur d’hébergement sur le serveur Edge.

Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell pour les applets de commande suivantes :

  - [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))

  - [New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))

<div>


> [!IMPORTANT]
> Avant d’effectuer ces étapes, vous devez créer un enregistrement SRV DNS externe pour le service d’hébergement Exchange. Pour plus d’informations, consultez <A href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">la rubrique créer un enregistrement SRV DNS pour l’intégration à la messagerie unifiée Exchange hébergée</A>.



</div>

<div>

## <a name="to-configure-the-edge-server-for-federation"></a>Pour configurer le serveur Edge pour la Fédération

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Exécutez la cmdlet Set-CsAccessEdgeConfiguration pour configurer le serveur pour la Fédération. Par exemple, exécutez :
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -AllowFederatedUsers 1 -EnablePartnerDiscovery 0
    
    L’exemple qui précède définit les paramètres suivants :
    
      - **UseDnsSrvRouting** indique que les serveurs Edge doivent reposer sur les enregistrements DNS SRV lors de l’envoi et la réception des demandes de fédération.
    
      - **AllowFederatedUsers** indique si des utilisateurs internes sont autorisés à communiquer avec des utilisateurs de domaines fédérés. Cette propriété détermine également si des utilisateurs internes peuvent communiquer avec des utilisateurs de domaines fractionnés.
    
      - **EnablePartnerDiscovery** spécifie si Lync Server utilise des enregistrements DNS pour essayer de découvrir des domaines partenaires non répertoriés dans la liste des domaines autorisés Active Directory. Si la valeur est false, Lync Server 2013 se fédérera uniquement avec les domaines figurant dans la liste des domaines autorisés. Ce paramètre est requis si vous utilisez le routage de service DNS. Dans la plupart des déploiements, la valeur est définie sur False pour empêcher l’ouverture de la fédération à tous les partenaires.

</div>

<div>

## <a name="to-replicate-data-to-the-edge-server-and-verify-the-replication"></a>Pour répliquer des données sur le serveur Edge et vérifier la réplication

  - Vérifiez que la réplication vers le serveur Edge est terminée. Pour la procédure, voir [Vérifier la connectivité entre les serveurs internes et les serveurs Edge dans Lync Server 2013](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md).

</div>

<div>

## <a name="to-create-a-hosting-provider-on-the-edge-server"></a>Pour créer un fournisseur d’hébergement sur le serveur Edge

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Exécutez la cmdlet **New-CsHostingProvider** pour configurer le fournisseur d’hébergement. Par exemple, exécutez :
    
        New-CsHostingProvider -Identity Fabrikam.com -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFQDN "proxyserver.fabrikam.com" -IsLocal $False -VerificationLevel UseSourceVerification
    
    L’exemple qui précède définit les paramètres suivants :
    
      - **Identity** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez, dans cet exemple, **fabrikam.com**. Notez que la commande échoue si un fournisseur existant a déjà été configuré avec cette identité.
    
      - **Enabled** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée. Les messages ne peuvent pas être échangés entre les deux organisations tant que cette valeur n’est pas définie sur **true**.
    
      - **EnabledSharedAddressSpace** indique si le fournisseur d’hébergement est utilisé dans un scénario d’espace d’adressage SIP partagé (domaine fractionné).
        
        <div>
        

        > [!NOTE]
        > Avant de définir <CODE>EnableSharedAddressSpace</CODE> sur true, essayez de résoudre l’enregistrement SRV de Fédération en interne. Si cet enregistrement ne peut pas être résolu en interne, vous devez créer les enregistrements, _sipfederationtls. _tcp. &lt;domain&gt; et _sip. _tls. &lt;domaine&gt; dans le DNS interne. Ces enregistrements doivent pointer vers l’adresse IP externe de l’interface d’accès du serveur Edge.

        
        </div>
    
      - **HostsOCSUsers** indique si le fournisseur d’hébergement est utilisé pour héberger les comptes Lync Server 2013. Si la **valeur est false**, le fournisseur héberge d’autres types de comptes, tels que les comptes Microsoft Exchange.
    
      - **ProxyFQDN** spécifie le nom de domaine complet (FQDN) du serveur proxy utilisé par le fournisseur d’hébergement, dans cet exemple, **ProxyServer.fabrikam.com**. Cette valeur ne peut pas être modifiée. Si le fournisseur d’hébergement modifie son serveur proxy, vous devrez supprimer, puis recréer l’entrée pour ce fournisseur.
    
      - **IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans votre topologie Lync Server 2013.
    
      - **Verificationlevel** indique le niveau de vérification autorisé pour les messages échangés avec le fournisseur hébergé. Spécifiez **UseSourceVerification**, qui s’appuie sur le niveau de vérification inclus dans les messages envoyés par le fournisseur d’hébergement. Si ce niveau n’est pas spécifié, alors le message sera rejeté comme message non vérifiable.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Exportation de votre topologie Lync Server 2013 et copie vers le support externe pour l’installation Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)  


[Vérifier la connectivité entre les serveurs internes et les serveurs Edge dans Lync Server 2013](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)  


[New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

