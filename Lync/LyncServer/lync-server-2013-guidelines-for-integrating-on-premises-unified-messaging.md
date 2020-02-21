---
title: 'Lync Server 2013 : instructions pour l’intégration de la messagerie unifiée locale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Guidelines for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398656(v=OCS.15)
ms:contentKeyID: 48184681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71d6fc97a0b8c96758344dea12a0720d5ad049ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>Instructions pour l’intégration de la messagerie unifiée locale et de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-25_

Vous trouverez ci-dessous des conseils et des pratiques recommandées à prendre en compte lors du déploiement de voix entreprise :

<div>


> [!IMPORTANT]  
> La messagerie unifiée Exchange prend en charge IPv6 uniquement si vous utilisez également UCMA 4.



</div>

  - Déployez un serveur Lync Server 2013 Standard Edition ou un pool frontal. Pour plus d’informations sur l’installation, voir [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) dans la documentation de déploiement.

  - Collaborez avec les administrateurs Exchange pour confirmer les tâches que chacun effectuera afin de garantir une intégration réussie en toute transparence.

  - Déployez les rôles serveur de boîtes aux lettres Exchange dans chaque forêt de messagerie unifiée Exchange où vous souhaitez activer les utilisateurs pour la messagerie unifiée Exchange. Pour plus d’informations sur l’installation des rôles Exchange Server, voir la documentation de Microsoft Exchange Server 2013.
    
    <div>
    

    > [!IMPORTANT]  
    > Lorsque la messagerie unifiée Exchange est installée, elle est configurée pour utiliser un certificat auto-signé.<BR>Toutefois, le certificat auto-signé ne permet pas à Lync Server 2013 et à la messagerie unifiée Exchange de s’approuver mutuellement, c’est pourquoi il est nécessaire de demander un certificat distinct auprès d’une autorité de certification approuvée par les deux serveurs.

    
    </div>

  - Si Lync Server 2013 et la messagerie unifiée Exchange sont installés dans des forêts différentes, configurez chaque forêt Exchange pour qu’elle approuve la forêt Lync Server 2013 et la forêt Lync Server 2013 pour approuver chaque forêt Exchange. Définissez également les paramètres de messagerie unifiée Exchange des utilisateurs sur les objets utilisateur de la forêt Lync Server 2013, généralement à l’aide d’un script ou d’un outil entre forêts, tel que Identity Lifecycle Manager (ILM).

  - Si nécessaire, installez la console de gestion Exchange pour gérer vos serveurs de messagerie unifiée.

  - Procurez-vous des numéros de téléphone valides pour Outlook Voice Access et le standard automatique.

  - Si vous utilisez une version de la messagerie unifiée Exchange antérieure à Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordonnez les noms des plans de numérotation URI SIP de messagerie unifiée Exchange et des plans de numérotation voix entreprise.

<div>

## <a name="deploying-redundant-exchange-um-servers"></a>Déploiement de serveurs de messagerie unifiée Exchange redondants :

<div>


> [!IMPORTANT]  
> Nous vous recommandons de déployer au moins deux serveurs sur lesquels les services de messagerie unifiée Exchange sont en cours d’exécution pour chaque plan de numérotation URI SIP de messagerie unifiée Exchange que vous configurez pour votre organisation. En plus de fournir une capacité étendue, le déploiement de serveurs redondants offre une haute disponibilité. En cas de défaillance du serveur, Lync Server 2013 peut être configuré pour basculer sur un autre serveur.



</div>

Les configurations de l’exemple suivant fournissent la résistance à la messagerie unifiée Exchange.

**Exemple 1 : résistance de la messagerie unifiée Exchange**

![Exemple de messagerie unifiée Exchange 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exemple de messagerie unifiée Exchange 1")

Dans l’exemple 1, les serveurs de messagerie unifiée Exchange 1 et 2 sont activés dans le centre de données Tukwila, et les serveurs de messagerie unifiée Exchange 3 et 4 sont activés dans le centre de données Dublin. En cas de panne de messagerie unifiée Exchange dans Tukwila, les enregistrements A DNS (Domain Name System) A pour les serveurs 1 et 2 doivent être configurés de façon à POINTER respectivement vers les serveurs 3 et 4. En cas de panne de messagerie unifiée Exchange dans Dublin, les enregistrements DNS A pour les serveurs 3 et 4 doivent être configurés de façon à POINTER respectivement vers les serveurs 1 et 2.

<div>


> [!NOTE]  
> Pour Exemple 1, vous devez également affecter l’un des certificats suivants sur chaque serveur de messagerie unifiée Exchange : 
> <UL>
> <LI>
> <P>Utilisez un certificat avec un caractère générique dans l’autre nom du sujet (SAN).</P>
> <LI>
> <P>Placez le nom de domaine complet (FQDN) de chacun des quatre serveurs de messagerie unifiée Exchange dans le SAN.</P></LI></UL>



</div>

**Exemple 2 : résistance de la messagerie unifiée Exchange**

![Exemple de messagerie unifiée Exchange 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exemple de messagerie unifiée Exchange 2")

Dans l’exemple 2, dans des conditions de fonctionnement normales, les serveurs de messagerie unifiée Exchange 1 et 2 sont activés dans le centre de données Tukwila, et les serveurs de messagerie unifiée Exchange 3 et 4 sont activés dans le centre de données Dublin. Les quatre serveurs sont tous inclus dans le plan de numérotation URI SIP des utilisateurs Tukwila, toutefois les serveurs 3 et 4 sont désactivés. Dans le cas d’une défaillance d’un serveur de messagerie unifiée Exchange dans Tukwila, par exemple, les serveurs de messagerie unifiée Exchange 1 et 2 doivent être désactivés et les serveurs de messagerie unifiée Exchange 3 et 4 activés afin que le trafic de messagerie unifiée Exchange Tukwila soit acheminé vers les serveurs dans Dublin.

Pour plus d’informations sur l’activation ou la désactivation de la messagerie unifiée sur Exchange 2013, voir « intégration de la [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372)messagerie unifiée Exchange 2013 à Lync Server » à l’adresse.

Pour plus d’informations sur l’activation ou la désactivation de la messagerie unifiée sur Microsoft Exchange Server 2010, voir :

  - « Activer la messagerie unifiée sur Exchange 2010 [https://go.microsoft.com/fwlink/p/?LinkId=204418](https://go.microsoft.com/fwlink/p/?linkid=204418)» à l’adresse.

  - « Désactiver la messagerie unifiée sur Exchange 2010 [https://go.microsoft.com/fwlink/p/?LinkId=204416](https://go.microsoft.com/fwlink/p/?linkid=204416)» à l’adresse.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Processus de déploiement pour l’intégration de la messagerie unifiée locale et de Lync Server 2013](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

