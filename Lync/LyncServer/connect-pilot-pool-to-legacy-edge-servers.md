---
title: Connexion du pool pilote aux serveurs Edge hérités
TOCTitle: Connexion du pool pilote aux serveurs Edge hérités
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49891528
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Connexion du pool pilote aux serveurs Edge hérités

 

_**Dernière rubrique modifiée :** 2012-09-29_

Après le déploiement de Lync Server 2013, vous devez configurer un itinéraire de fédération pour le site. Pour permettre l’utilisation de l’itinéraire fédéré utilisé par Lync Server 2010, Lync Server 2013 doit être configuré à cet effet.

Pour activer le site Lync Server 2013 afin qu’il utilise le directeur ou le serveur Edge du déploiement Lync Server 2010, utilisez le générateur de topologie pour associer le pool Edge hérité.

## Pour associer le pool Edge hérité à l’aide du générateur de topologie

1.  Ouvrez le **Générateur de topologie**.

2.  Sélectionnez votre site, qui est affiché juste en dessous du nœud **Lync Server**.

3.  Dans le menu **Actions**, cliquez sur **Modifier les propriétés**.

4.  Dans le volet gauche, sélectionnez **Itinéraire de fédération**.

5.  Sous **Attribution de l’itinéraire de fédération du site**, sélectionnez **Activer la fédération SIP**, puis le directeur Lync Server 2010 ou le serveur Edge Lync Server 2010 si aucun directeur n’est répertorié.
    
    ![Modifier les propriétés, page Itinéraire de fédération](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Modifier les propriétés, page Itinéraire de fédération")  

6.  Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.

7.  Dans le générateur de topologie, sous le nœud Lync Server 2013, accédez au **Serveur Standard Edition** ou aux **Pools frontaux Enterprise Edition**, cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.

8.  Sous **Associations**, activez la case à cocher en regard de **Associer un pool de serveurs Edge (pour les composants médias)**.

9.  Dans la liste, sélectionnez le serveur Edge hérité.
    
    ![Boîte de dialogue Modifier les propriétés, sélectionner le serveur Edge hérité](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, sélectionner le serveur Edge hérité")  

10. Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.

11. Dans **Générateur de topologie**, sélectionnez le nœud de niveau supérieur, **Lync Server**.

12. Dans le menu **Actions**, cliquez sur **Publier la topologie**, puis cliquez sur **Suivant**.

13. Quand l’**Assistant Publication** est terminé, cliquez sur **Terminer**.

