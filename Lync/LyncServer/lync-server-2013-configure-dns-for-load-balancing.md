---
title: 'Lync Server 2013 : Configuration du DNS pour l’équilibrage de charge'
TOCTitle: Configuration du DNS pour l’équilibrage de charge
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398251(v=OCS.15)
ms:contentKeyID: 49296422
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration du DNS pour l’équilibrage de charge dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine au moins en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.

L’équilibrage de charge DNS permet d’équilibrer le trafic réseau propre à Lync Server 2013, notamment le trafic SIP et le trafic multimédia. L’équilibrage de charge DNS est pris en charge pour les pools frontaux, les pools de serveurs Edge, les pools de serveurs directeurs et les pools de serveurs de médiation autonomes. Deux noms de domaine complets (FQDN) doivent être définis pour un pool configuré pour utiliser l’équilibrage de charge DNS à savoir : le nom de domaine complet standard du pool utilisé par l’équilibrage de charge DNS (par exemple, pool1.contoso.com) et résolu en adresse IP pour chaque serveur dans le pool et un autre nom de domaine complet pour les services web du pool (par exemple, web1.contoso.net), résolu en adresse IP virtuelle du pool. Pour plus d’informations sur l’équilibrage de charge DNS, reportez-vous à [Équilibrage de charge DNS dans Lync Server 2013](lync-server-2013-dns-load-balancing.md) dans la documentation de planification.

> [!NOTE]  
> L’équilibrage de la charge matérielle est toujours requis pour le trafic HTTPS du client au serveur.

Avant d’utiliser l’équilibrage de charge DNS, procédez comme suit :

1.  Remplacer le nom de domaine complet du pool des services web internes.
    
    > [!WARNING]  
    > Si vous choisissez de remplacer le nom des services web internes par un nom de domaine complet personnalisé, chaque nom de domaine complet doit être distinct des autres noms de pool de serveurs frontaux, directeur ou pool de directeurs.

2.  Créer des enregistrements d’hôte DNS A pour résoudre le nom de domaine complet (FQDN) du pool en adresse IP pour chaque serveur dans le pool.

3.  Activer la randomisation d’adresse IP ou, pour l’équilibrage de charge DNS sous Windows Server, activez le round robin.
    
    > [!NOTE]  
    > La fonctionnalité de tourniquet (round robin) doit être activée par défaut.

## Pour remplacer le nom de domaine complet des services web internes

1.  Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.

2.  Dans l’arborescence de la console, développez le nœud des pools frontaux Enterprise Edition.

3.  Cliquez avec le bouton droit sur le pool, cliquez sur **Modifier les propriétés** , puis cliquez sur **Services web** .

4.  Sous **Services web internes** , activez la case à cocher **Remplacer le nom de domaine complet** .

5.  Tapez le nom de domaine complet du pool résolu en adresse IP physique pour chaque serveur dans le pool.

6.  Sous **Services web externes** , tapez le nom de domaine complet du pool externe résolu en adresse IP virtuelle du pool, puis cliquez sur **OK** .

7.  Dans l’arborescence de la console, cliquez sur **Lync Server 2013**, puis dans le volet **Actions** , cliquez sur **Publier la topologie** .

## Pour créer des enregistrements d’hôte DNS (A) pour tous les serveurs du pool interne

1.  Cliquez sur **Démarrer** , sur **Tous les programmes** , sur **Outils d’administration** , puis sur **DNS** .

2.  Dans **Gestionnaire DNS** , cliquez sur le serveur DNS qui gère les enregistrements pour le développer.

3.  Cliquez sur le nœud **Zones de recherche directes** pour le développer.

4.  Cliquez avec le bouton droit sur le domaine DNS auquel vous devez ajouter des enregistrements, puis cliquez sur **Nouvel hôte (A ou AAAA)** .

5.  Dans la zone **Nom** , tapez le nom de l’enregistrement de l’hôte (le nom du domaine est automatiquement ajouté).

6.  Dans la zone Adresse IP, tapez l’adresse IP du serveur frontal, puis sélectionnez **Créer un pointeur d’enregistrement PTR associé** ou **Autoriser tout utilisateur identifié à mettre à jour les enregistrements DNS avec le même nom de propriétaire** , le cas échéant.

7.  Continuez à créer des enregistrements pour tous les serveurs frontaux membres qui participeront à l’équilibrage de charge DNS.
    
    Par exemple, pour un pool nommé pool1.contoso.com et trois serveurs frontaux, vous devrez créer les entrées DNS suivantes :
    
    
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
    
    Pour plus d’informations sur la création d’enregistrements d’hôte DNS (A), reportez-vous à [Configuration des enregistrements hôte DNS pour Lync Server 2013](lync-server-2013-configure-dns-host-records.md).

## Pour activer le round robin pour Windows Server

1.  Cliquez sur **Démarrer** , sur **Tous les programmes** , sur **Outils d’administration** , puis sur **DNS** .

2.  Développez **DNS** , cliquez avec le bouton droit sur le serveur DNS que vous souhaitez configurer, puis cliquez sur **Propriétés** .

3.  Cliquez sur l’onglet **Avancé** , sélectionnez **Activer la fonction Round Robin** et **Activer le tri de masques réseau** , puis cliquez sur **OK** .
    
    ![Boîte de dialogue DNS Round Robin](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "Boîte de dialogue DNS Round Robin")

> [!NOTE]  
> Cette fonctionnalité doit être activée par défaut.

## Voir aussi

#### Concepts

[Équilibrage de charge DNS dans Lync Server 2013](lync-server-2013-dns-load-balancing.md)

