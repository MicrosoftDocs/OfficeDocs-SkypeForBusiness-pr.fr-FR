---
title: 'Lync Server 2013 : Architecture d’intégration de messagerie unifiée Exchange hébergée'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange UM integration architecture
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48183222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2991bb35298534943d030b04c1cae7a438318c62
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831065"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a>Architecture d’intégration de messagerie unifiée Exchange hébergée dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-25_

L’application de routage de ExUM Lync Server 2013 prend en charge l’intégration avec un déploiement de messagerie unifiée Exchange local (MU), avec la messagerie unifiée hébergée par un fournisseur de service ou avec une combinaison des deux. Le diagramme suivant présente les trois possibilités.

**Intégration avec un déploiement Exchange UM local et deux fournisseurs Exchange hébergés**

![Déploiement de la messagerie unifiée Exchange Server en local] (images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Déploiement de la messagerie unifiée Exchange Server en local")

Les modes suivants sont pris en charge:

  - **Déploiement local:** Lync Server 2013 et la messagerie unifiée Exchange sont tous deux déployés sur des serveurs locaux au sein de votre entreprise.

  - **Déploiement sur site:** Lync Server 2013 est déployé sur des serveurs locaux au sein de votre entreprise et la messagerie unifiée Exchange est hébergée dans une installation de prestataire de services en ligne, telle qu’un centre de données Microsoft Exchange Online.

  - **Déploiement mixte:** Votre déploiement de Lync Server 2013 dispose de certaines boîtes aux lettres d’utilisateurs hébergées sur des serveurs Exchange locaux au sein de votre entreprise, et de certaines boîtes aux lettres dans un centre de données de service Exchange hébergé.
    
    <div>
    

    > [!NOTE]  
    > Le déploiement mixte peut être utilisé en tant que solution de transition lors de l’évaluation et de la migration par phases des utilisateurs vers la messagerie unifiée Exchange hébergée, ou d’une solution permanente si vous choisissez de limiter les services de messagerie unifiée d’échange des utilisateurs en local après le transfert d’autres utilisateurs.

    
    </div>

<div>

## <a name="shared-sip-address-space"></a>Espace d’adressage SIP partagé

Pour intégrer Lync Server 2013 à un déploiement Exchange UM local, vous accordez l’autorisation Lync Server 2013 aux objets services de domaine Active Directory UM. Toutefois, cette approche ne fonctionne pas pour l’intégration à la messagerie unifiée Exchange hébergée, car Lync Server 2013 et la messagerie unifiée Exchange sont installés dans des forêts distinctes sans approbation.

Pour intégrer Lync Server 2013 et la messagerie unifiée Exchange hébergée, vous devez configurer un *espace d’adressage SIP partagé*. Dans cette configuration, le même espace d’adressage de domaine SIP est disponible pour Lync Server 2013 et le fournisseur de service de messagerie unifiée Exchange hébergé.

<div>


> [!NOTE]  
> L’utilisation de l’espace d’adressage SIP partagé est semblable à celle utilisée dans un environnement Lync Server 2013 multiplateforme, dans lequel certains utilisateurs sont hébergés dans le déploiement local, et certains sont hébergés dans un déploiement hébergé (par exemple, Lync Online). Le domaine SIP est fractionné entre eux. Lorsque vous intégrez Lync Server 2013 à une messagerie unifiée Exchange hébergée, veillez à inclure le fournisseur de service de messagerie unifiée Exchange dans l’espace d’adressage SIP partagé.



</div>

Pour configurer l’espace d’adressage SIP partagé à des fins d’intégration à un fournisseur de service de messagerie unifiée Exchange, vous devez configurer votre serveur Edge comme suit:

1.  Configurez le serveur Edge pour la Fédération en exécutant l’applet de commande **Set-CsAccessEdgeConfiguration** pour définir les paramètres suivants:
    
      - **UseDnsSrvRouting ** indique que les serveurs Edge doivent reposer sur les enregistrements DNS SRV lors de l’envoi et la réception des demandes de fédération.
    
      - **AllowFederatedUsers ** indique si des utilisateurs internes sont autorisés à communiquer avec des utilisateurs de domaines fédérés. Cette propriété détermine également si des utilisateurs internes peuvent communiquer avec des utilisateurs de domaines fractionnés.
    
      - **EnablePartnerDiscovery** spécifie si Lync Server 2013 utilisera les enregistrements DNS pour essayer de détecter des domaines de partenariat qui ne sont pas répertoriés dans la liste des domaines autorisés Active Directory. Si faux, Lync Server 2013 se fédérera uniquement avec les domaines qui se trouvent sur la liste des domaines autorisés. Ce paramètre est requis si vous utilisez le routage de service DNS. Dans la plupart des déploiements, la valeur est définie sur False pour empêcher l’ouverture de la fédération à tous les partenaires.

2.  Répliquez le magasin de gestion central sur le serveur Edge et vérifiez la réplication. Pour plus d’informations, reportez-vous [à exporter votre topologie Lync Server 2013 et à la copier sur média externe pour l’installation Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) dans la documentation de déploiement.

3.  Configurez un *fournisseur d’hébergement* sur le serveur Edge en exécutant l’applet de commande **New-CsHostingProvider** pour définir les paramètres suivants:
    
      - **Identity** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez, par exemple, la **messagerie unifiée Exchange hébergée**.
    
      - **Enabled ** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée. Doit avoir la valeur **true**.
    
      - **EnabledSharedAddressSpace** indique si le fournisseur d’hébergement sera utilisé dans un scénario d’espace d’adressage SIP partagé. Doit avoir la valeur **true**.
    
      - **HostsOCSUsers** indique si le fournisseur d’hébergement est utilisé pour héberger des comptes Lync Server 2013. Doit être défini sur **false**.
    
      - **ProxyFQDN** spécifie le nom de domaine complet (FQDN) du serveur proxy utilisé par le fournisseur d’hébergement (par exemple, **ProxyServer.fabrikam.com**. Pour obtenir ces informations, contactez votre fournisseur d’hébergement. Cette valeur ne peut pas être modifiée. Si le fournisseur d’hébergement a modifié son serveur proxy, vous devez supprimer, puis recréer l’entrée pour ce fournisseur.
    
      - **IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans votre topologie Lync Server 2013. Doit être défini sur **false**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

