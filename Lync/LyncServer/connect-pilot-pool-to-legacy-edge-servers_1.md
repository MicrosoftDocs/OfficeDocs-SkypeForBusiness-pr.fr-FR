---
title: Connexion du pool pilote aux serveurs Edge hérités
TOCTitle: Connexion du pool pilote aux serveurs Edge hérités
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205136(v=OCS.15)
ms:contentKeyID: 49298378
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Connexion du pool pilote aux serveurs Edge hérités

 

_**Dernière rubrique modifiée :** 2012-10-02_

Après le déploiement de Lync Server 2013, aucun itinéraire de fédération n’est configuré pour le site. Pour permettre l’utilisation de l’itinéraire fédéré utilisé par Office Communications Server 2007 R2, Lync Server 2013 doit être configuré à cet effet.

Pour permettre au site Lync Server 2013 d’utiliser le directeur et le serveur Edge du BackCompatSite, utilisez le générateur de topologie pour associer le pool Edge hérité.

## Pour associer le pool Edge hérité à l’aide du générateur de topologie

1.  Ouvrez la topologie du pool pilote dans le générateur de topologie.

2.  Sélectionnez votre site Lync Server 2013.

3.  Dans le menu **Actions** , cliquez sur **Modifier les propriétés** .

4.  Sous **Attribution de l’itinéraire de fédération du site** , sélectionnez **Activer la fédération SIP** , puis le directeur Office Communications Server 2007 R2, ou le serveur Edge Office Communications Server 2007 R2 si aucun directeur n’est répertorié.
    
    ![Boîte de dialogue Modifier les propriétés, page Itinéraire de fédération](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, page Itinéraire de fédération")  

5.  Cliquez sur **OK** pour fermer la page **Modifier les propriétés** .

6.  Dans le générateur de topologie, sous le nœud Lync Server 2013, accédez au **Serveur Standard Edition** ou aux **Pools frontaux Enterprise Edition** , cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés** .

7.  Sous **Associations** , activez la case à cocher en regard de **Associer un pool de serveurs Edge (pour les composants médias)** .

8.  Dans la liste, sélectionnez l’interface de serveur Edge pour le BackCompatSite.
    
    ![Boîte de dialogue Modifier les propriétés, page Général](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, page Général")  

9.  Cliquez sur **OK** pour fermer la page **Modifier les propriétés** .

10. Dans le **Générateur de topologie** , sélectionnez le nœud de niveau supérieur, **Lync Server** .

11. Dans le menu **Actions** , cliquez sur **Publier la topologie** , puis cliquez sur **Suivant** .

12. Quand l’**Assistant Publication** est terminé, cliquez sur **Terminer** .

