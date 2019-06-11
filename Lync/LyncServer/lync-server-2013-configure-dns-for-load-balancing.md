---
title: 'Lync Server 2013 : Configuration du DNS pour l’équilibrage de charge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS for load balancing
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398251(v=OCS.15)
ms:contentKeyID: 48183540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e370d3b66e82b02bd5668fc1c9cab4ee41da759
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a>Configuration du DNS pour l’équilibrage de charge dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-01_

Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine au minimum en tant que membre du groupe administrateurs de domaine ou membre du groupe DnsAdmins.

L’équilibrage de charge DNS (Domain Name System) équilibre le trafic réseau unique vers Lync Server 2013, comme le trafic SIP et le trafic multimédia. L’équilibrage de charge DNS est pris en charge pour les listes frontales, les pools de périphériques, les pools de directeurs et les pools de médiation autonomes. Un pool configuré pour utiliser l’équilibrage de charge DNS doit avoir deux noms de domaine complets (FQDN) définis: le nom de domaine complet (FQDN) du pool standard utilisé par l’équilibrage de charge DNS (par exemple, pool1.contoso.com) et résolu vers l’IPs physique des serveurs du pool. et un autre nom de domaine complet (par exemple, web1.contoso.net) pour les services Web du pool, qui est résolu sur l’adresse IP virtuelle du pool. Pour plus d’informations sur l’équilibrage de charge DNS, voir [équilibrage de charge DNS dans Lync Server 2013](lync-server-2013-dns-load-balancing.md) dans la documentation de planification.

<div>


> [!NOTE]  
> L’équilibrage de charge matérielle est toujours requis pour le trafic du client vers le serveur HTTPs.



</div>

Pour pouvoir utiliser l’équilibrage de charge DNS, vous devez procéder comme suit:

1.  Remplacez le nom de domaine complet (FQDN) du pool de services Web interne.
    
    <div>
    

    > [!WARNING]  
    > Si vous décidez de remplacer les services Web internes par un nom de domaine complet autonome, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool de réalisateur.

    
    </div>

2.  Créer des enregistrements DNS A pour résoudre le nom de domaine complet (FQDN) du pool en adresses IP de tous les serveurs du pool.

3.  Activez la randomisation des adresses IP ou, pour le DNS de Windows Server, activez la répétition alternée.
    
    <div>
    

    > [!NOTE]  
    > La répétition alternée doit être activée par défaut.

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a>Pour ignorer le nom de domaine complet des services Web internes

1.  Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.

2.  Dans l’arborescence de la console, développez le nœud Pools front end Enterprise Edition.

3.  Cliquez avec le bouton droit sur la liste, cliquez sur **modifier les propriétés**, puis cliquez sur **services Web**.

4.  Sous les **services Web internes**, activez la case à cocher **remplacer le FQDN** .

5.  Tapez le nom de domaine complet (FQDN) du pool qui se résout aux adresses IP physiques des serveurs du pool.

6.  Sous **services Web externes**, tapez le nom de domaine complet du pool externe qui se résout aux adresses IP virtuelles de la liste, puis cliquez sur **OK**.

7.  À partir de l’arborescence de la console, cliquez sur **Lync Server 2013**, puis, dans le volet **actions** , cliquez sur **publier la topologie**.

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a>Pour créer des enregistrements d’hôte DNS (A) pour tous les serveurs de pool interne

1.  Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Outils d’administration**, puis sur **DNS**.

2.  Dans le **Gestionnaire DNS**, cliquez sur le serveur DNS qui gère vos enregistrements pour le développer.

3.  Cliquez sur **transférer des zones de recherche** pour les développer.

4.  Cliquez avec le bouton droit sur le domaine DNS auquel vous devez ajouter des enregistrements, puis cliquez sur **nouvel hôte (A ou AAAA)**.

5.  Dans la zone **Nom**, tapez le nom de l’enregistrement de l’hôte (le nom du domaine est automatiquement ajouté).

6.  Dans la zone adresse IP, tapez l’adresse IP du serveur principal individuel, puis sélectionnez créer un **pointeur associé (PTR)** , ou **autorisez les utilisateurs authentifiés à mettre à jour les enregistrements DNS portant le même nom de propriétaire**, le cas échéant.

7.  Continuez à créer des enregistrements pour tous les serveurs frontaux de membre qui feront partie de l’équilibrage de charge DNS.
    
    Par exemple, si vous avez un pool intitulé pool1.contoso.com et trois serveurs front-end, vous devez créer les entrées DNS suivantes:
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>FQDN</th>
    <th>Type</th>
    <th>Données</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>Hôte (A)</p></td>
    <td><p>192.168.1.1</p></td>
    </tr>
    <tr class="even">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>Hôte (A)</p></td>
    <td><p>192.168.1.2</p></td>
    </tr>
    <tr class="odd">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>Hôte (A)</p></td>
    <td><p>192.168.1.3</p></td>
    </tr>
    </tbody>
    </table>
    
    Pour plus d’informations sur la création d’enregistrements DNS Host (A), voir [configurer les enregistrements d’hôte DNS pour Lync Server 2013](lync-server-2013-configure-dns-host-records.md).

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a>Pour activer le tourniquet cyclique pour Windows Server

1.  Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Outils d’administration**, puis sur **DNS**.

2.  Développez **DNS**, cliquez avec le bouton droit sur le serveur DNS à configurer, puis cliquez sur **Propriétés**.

3.  Cliquez sur l’onglet **avancé** , sélectionnez **activer la répétition alternée** et activez l’ordre de tri des **masques**net, puis cliquez sur **OK**.
    
    ![Boîte de dialogue de répétition alternée DNS] (images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "Boîte de dialogue de répétition alternée DNS")

<div>


> [!NOTE]  
> Cette fonctionnalité doit être activée par défaut.



</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Équilibrage de charge DNS dans Lync Server 2013](lync-server-2013-dns-load-balancing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

