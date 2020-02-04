---
title: 'Lync Server 2013 : Instructions d’intégration de la messagerie unifiée locale'
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
ms.openlocfilehash: 3f3e57245f0a8edf5b545f9a67547e6be6f63399
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>Instructions d’intégration de la messagerie unifiée locale et de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-25_

Les instructions ci-dessous sont des directives et des pratiques recommandées à envisager lors du déploiement de Voix Entreprise :

<div>


> [!IMPORTANT]  
> La messagerie unifiée Exchange prend en charge le protocole IPv6 uniquement si vous utilisez également UCMA 4.



</div>

  - Déploiement d’un serveur Lync Server 2013 Standard Edition ou d’un pool frontal. Pour plus d’informations sur l’installation, voir [déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md) dans la documentation de déploiement.

  - Collaborez avec les administrateurs Exchange pour confirmer les tâches que chacun effectuera afin de garantir une intégration réussie en toute transparence.

  - Déployez les rôles de serveur de boîte aux lettres Exchange dans chaque forêt de messagerie unifiée Exchange dans laquelle vous souhaitez autoriser les utilisateurs pour la messagerie unifiée Exchange. Pour plus d’informations sur l’installation des rôles du serveur Exchange, voir la documentation Microsoft Exchange Server 2013.
    
    <div>
    

    > [!IMPORTANT]  
    > Lorsque la messagerie unifiée (MU) Exchange est installée, elle est configurée pour utiliser un certificat auto-signé.<BR>En revanche, le certificat auto-signé ne permet pas à Lync Server 2013 et à la messagerie unifiée Exchange d’approuver mutuellement, ce qui signifie qu’il est nécessaire de demander un certificat distinct auprès d’une autorité de certification approuvée par les deux serveurs.

    
    </div>

  - Si Lync Server 2013 et la messagerie unifiée Exchange sont installés dans différentes forêts, configurez chaque forêt Exchange pour approuver la forêt Lync Server 2013 et la forêt Lync Server 2013 pour approuver chaque forêt Exchange. Par ailleurs, définissez les paramètres de messagerie unifiée Exchange des utilisateurs sur les objets utilisateur dans la forêt 2013 du serveur Lync, en général à l’aide d’un script ou d’un outil multiplateforme, tel qu’Identity Lifecycle Manager (ILM).

  - Si nécessaire, installez la console de gestion Exchange pour gérer vos serveurs de messagerie unifiée.

  - Procurez-vous des numéros de téléphone valides pour Outlook Voice Access et le standard automatique.

  - Si vous utilisez une version d’Exchange UM antérieure à Microsoft Exchange Server 2010 Service Pack 1 (SP1), les noms de coordonnées des plans de numérotation URI SIP de messagerie unifiée et les plans de numérotation vocale d’entreprise.

<div>

## <a name="deploying-redundant-exchange-um-servers"></a>Déploiement de serveurs de messagerie unifiée Exchange redondants :

<div>


> [!IMPORTANT]  
> Nous vous recommandons de déployer un minimum de deux serveurs sur lesquels les services de messagerie unifiée Exchange s’exécutent pour chaque plan de numérotation URI SIP Exchange UM que vous configurez pour votre organisation. Le déploiement de serveurs redondants fournit non seulement une capacité étendue, mais offre également une disponibilité élevée. En cas de panne du serveur, Lync Server 2013 peut être configuré pour basculer vers un autre serveur.



</div>

Les configurations de l’exemple ci-dessous fournissent la résistance à la messagerie unifiée Exchange.

**Exemple 1 : résistance de la messagerie unifiée Exchange**

![Exemple de messagerie unifiée Exchange 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exemple de messagerie unifiée Exchange 1")

Dans l’exemple 1, les serveurs de messagerie unifiée Exchange 1 et 2 sont activés dans le centre de données Tukwila, et les serveurs de messagerie unifiée Exchange 3 et 4 sont activés dans le centre de données Dublin. En cas de défaillance de la messagerie unifiée Exchange dans Tukwila, les enregistrements DNS A pour les serveurs 1 et 2 doivent être configurés de manière à pointer respectivement vers les serveurs 3 et 4. En cas de défaillance de la messagerie unifiée Exchange dans Dublin, les enregistrements DNS A pour les serveurs 3 et 4 doivent être configurés de manière à pointer respectivement vers les serveurs 1 et 2.

<div>


> [!NOTE]  
> Pour l’exemple 1, vous devez également affecter l’un des certificats ci-dessous sur chaque serveur de messagerie unifiée Exchange : 
> <UL>
> <LI>
> <P>Utilisez un certificat avec un caractère générique dans l’autre nom du sujet (SAN).</P>
> <LI>
> <P>Ajoutez le nom de domaine complet de chacun des quatre serveurs de messagerie unifiée Exchange dans l’autre nom du sujet.</P></LI></UL>



</div>

**Exemple 2 : résistance de la messagerie unifiée Exchange**

![Exemple 2 Exchange UM 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exemple 2 Exchange UM 2")

Dans l’exemple 2, dans des conditions de fonctionnement normales, les serveurs de messagerie unifiée Exchange 1 et 2 sont activés dans le centre de données Tukwila, et les serveurs de messagerie unifiée Exchange 3 et 4 sont activés dans le centre de données Dublin. Les quatre serveurs sont tous inclus dans le plan de numérotation URI SIP des utilisateurs Tukwila, toutefois les serveurs 3 et 4 sont désactivés. Dans le cas d’une défaillance d’un serveur de messagerie unifiée Exchange dans Tukwila, par exemple, les serveurs de messagerie unifiée Exchange 1 et 2 doivent être désactivés et les serveurs de messagerie unifiée Exchange 3 et 4 activés afin que le trafic de messagerie unifiée Exchange Tukwila soit acheminé vers les serveurs dans Dublin.

Pour plus d’informations sur l’activation ou la désactivation de la messagerie unifiée sur Exchange 2013, voir « intégration de la [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)messagerie unifiée Exchange 2013 avec Lync Server ».

Pour plus d’informations sur l’activation ou la désactivation de la messagerie unifiée sur Microsoft Exchange Server 2010, voir :

  - « Activez la messagerie unifiée sur Exchange 2010 [http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418)».

  - « Désactiver la messagerie unifiée sur Exchange 2010 [http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416)».

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Processus de déploiement pour l’intégration de la messagerie unifiée locale et de Lync Server 2013](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

