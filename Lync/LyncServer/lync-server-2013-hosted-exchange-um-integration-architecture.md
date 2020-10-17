---
title: 'Lync Server 2013 : architecture d’intégration de la messagerie unifiée Exchange hébergée'
description: 'Lync Server 2013 : architecture d’intégration de la messagerie unifiée Exchange hébergée.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM integration architecture
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48183222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2399fa421b59a5ea1fd83b1a86225fc12de1f2ca
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552460"
---
# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a>Architecture d’intégration de la messagerie unifiée Exchange hébergée dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-25_

L’application de routage ExUM de Lync Server 2013 prend en charge l’intégration à un déploiement de messagerie unifiée Exchange sur site, avec la messagerie unifiée Exchange hébergée par un fournisseur de services ou avec une combinaison des deux. Le diagramme suivant montre les trois possibilités.

**Intégration à un déploiement de messagerie unifiée Exchange sur site et à deux déploiements Exchange hébergés par des fournisseurs de service**

![Déploiement de la messagerie unifiée Lync Server Exchange sur site](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Déploiement de la messagerie unifiée Lync Server Exchange sur site")

Les modes suivants sont pris en charge :

  - **Déploiement sur site :** Lync Server 2013 et la messagerie unifiée Exchange sont tous deux déployés sur des serveurs locaux dans votre entreprise.

  - **Déploiement** intersites : Lync Server 2013 est déployé sur des serveurs locaux dans votre entreprise et la messagerie unifiée Exchange est hébergée dans une installation de fournisseur de services en ligne, telle qu’un centre de données Microsoft Exchange Online.

  - **Déploiement mixte :** Votre déploiement Lync Server 2013 comporte des boîtes aux lettres d’utilisateur hébergées sur des serveurs Exchange locaux dans votre entreprise et des boîtes aux lettres hébergées dans un centre de données de service Exchange hébergé.
    
    <div>
    

    > [!NOTE]  
    > Le déploiement mixte peut tenir lieu de solution de transition au cours de l’évaluation et de la migration progressive des utilisateurs vers un service de messagerie unifiée Exchange hébergé, ou de solution permanente, si vous décidez de conserver sur site les services de messagerie unifiée Exchange de certains utilisateurs après en avoir transféré d’autres.

    
    </div>

<div>

## <a name="shared-sip-address-space"></a>Espace d’adressage SIP partagé

Pour intégrer Lync Server 2013 avec un déploiement de messagerie unifiée Exchange local, vous devez accorder à Lync Server 2013 l’autorisation de lire les objets des services de domaine Active Directory de messagerie unifiée Exchange. Cette approche ne fonctionne pas pour l’intégration avec la messagerie unifiée Exchange hébergée, car Lync Server 2013 et la messagerie unifiée Exchange sont installés dans des forêts distinctes sans approbation.

Pour intégrer Lync Server 2013 à la messagerie unifiée Exchange hébergée, vous devez configurer un *espace d’adressage SIP partagé*. Dans cette configuration, le même espace d’adressage de domaine SIP est disponible pour Lync Server 2013 et pour le fournisseur de services de messagerie unifiée Exchange hébergé.

<div>


> [!NOTE]  
> L’utilisation de l’espace d’adressage SIP partagé est semblable à l’approche utilisée dans un environnement Lync Server 2013 intersites, dans lequel certains utilisateurs sont hébergés dans le déploiement local et d’autres sont hébergés dans un déploiement hébergé (par exemple, Lync Online). Le domaine SIP est fractionné entre les deux déploiements. Lorsque vous intégrez Lync Server 2013 avec la messagerie unifiée Exchange hébergée, vérifiez que vous incluez le fournisseur de services de messagerie unifiée Exchange dans l’espace d’adressage SIP partagé.



</div>

Pour configurer l’espace d’adressage SIP partagé en vue de l’intégration de Lync Server à un service de messagerie unifiée Exchange hébergé, vous devez configurer le serveur Edge comme suit :

1.  Configurez le serveur Edge pour la fédération en exécutant l’applet de commande **Set-CsAccessEdgeConfiguration** qui permet de définir les paramètres suivants :
    
      - **UseDnsSrvRouting** indique que les serveurs Edge doivent reposer sur les enregistrements DNS SRV lors de l’envoi et la réception des demandes de fédération.
    
      - **AllowFederatedUsers** indique si des utilisateurs internes sont autorisés à communiquer avec des utilisateurs de domaines fédérés. Cette propriété détermine également si des utilisateurs internes peuvent communiquer avec des utilisateurs de domaines fractionnés.
    
      - **EnablePartnerDiscovery** spécifie si Lync Server 2013 utilise des enregistrements DNS pour essayer de découvrir des domaines partenaires qui ne sont pas répertoriés dans la liste des domaines autorisés Active Directory. Si la valeur est false, Lync Server 2013 se fédérera uniquement avec les domaines qui se trouvent dans la liste des domaines autorisés. Ce paramètre est requis si vous utilisez le routage de service DNS. Dans la plupart des déploiements, la valeur est définie sur False pour empêcher l’ouverture de la fédération à tous les partenaires.

2.  Répliquer le magasin central de gestion sur le serveur Edge et vérifier la réplication. Pour plus d’informations, reportez-vous à la rubrique [Export Your Lync Server 2013 Topology and copy it to External Media for Edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) dans la documentation de déploiement.

3.  Configurez un *fournisseur d’hébergement* sur le serveur Edge en exécutant l’applet de commande **New-CsHostingProvider** qui permet de définir les paramètres suivants :
    
      - **Identity** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez, par exemple, **Messagerie unifiée Exchange hébergée**.
    
      - **Enabled** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée. La valeur doit être définie sur **True**.
    
      - **EnabledSharedAddressSpace** indique si le fournisseur d’hébergement sera utilisé dans un scénario d’espace d’adressage SIP partagé. La valeur doit être définie sur **True**.
    
      - **HostsOCSUsers** indique si le fournisseur d’hébergement est utilisé pour héberger les comptes Lync Server 2013. La valeur doit être définie sur **False**.
    
      - **ProxyFQDN** indique le nom de domaine complet du serveur proxy utilisé par le fournisseur d’hébergement, par exemple, **proxyserver.fabrikam.com**. Demandez cette information au fournisseur d’hébergement. Cette valeur ne peut pas être modifiée. Si le fournisseur d’hébergement change de serveur proxy, vous devrez supprimer et recréer l’entrée pour ce fournisseur.
    
      - **IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans votre topologie Lync Server 2013. La valeur doit être définie sur **False**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

