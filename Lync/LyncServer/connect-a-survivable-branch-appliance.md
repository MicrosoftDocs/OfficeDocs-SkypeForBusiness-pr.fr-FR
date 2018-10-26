---
title: Connexion d’une Survivable Branch Appliance
TOCTitle: Connexion d’une Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49891627
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Connexion d’une Survivable Branch Appliance

 

_**Dernière rubrique modifiée :** 2012-10-19_

Chaque SBA (Survivable Branch Appliance) est associée à un pool frontal qui sert de serveur d’inscription pour le SBA. Lorsque le pool frontal est migré vers Lync Server 2013, le SBA doit être dissocié du pool frontal Lync Server 2010 tandis que le pool est mis à niveau. Une fois le pool migré vers Lync Server 2013, le SBA peut être à nouveau associé au pool frontal mis à niveau. Cela implique la suppression du SBA de la topologie Lync Server 2010 héritée dans le générateur de topologie, puis l’ajout du SBA à la topologie Lync Server 2013. Les utilisateurs hébergés sur le Lync Server 2010 hérité doivent d’abord être déplacés vers un autre pool frontal avant d’être déplacés de nouveau du SBA vers la topologie. Une fois le SBA ajouté à la topologie Lync Server 2013, ces utilisateurs peuvent être ramenés dans le SBA. Ces étapes sont résumées ci-dessous :

1.  Déplacez les utilisateurs de succursale hébergés sur le Lync Server 2010 SBA hérité sur un autre pool frontal.

2.  Supprimez le SBA de la topologie Lync Server 2010 héritée pour déconnecter le pool frontal existant en tant que serveur d’inscription.

3.  Ajoutez le SBA à la topologie Lync Server 2013 et configurez ce nouveau pool frontal en tant que serveur d’inscription.

4.  Déplacez les utilisateurs de succursale vers le nouveau SBA Lync Server 2013.

**Ajouter le site de succursale SBA Lync Server 2010 à votre topologie**

1.  Ouvrez le **Générateur de topologie**.

2.  Dans le volet gauche, cliquez avec le bouton droit sur **Sites de succursale**, puis cliquez sur **Nouveau site de succursale**.

3.  Dans la boîte de dialogue **Définir un nouveau site de succursale**, cliquez sur **Nom**, puis entrez le nom du site de succursale.

4.  Cliquez sur **Description**, puis entrez une description explicite pour le site de la succursale (facultatif).

5.  Cliquez sur **Suivant**.

6.  Dans la boîte de dialogue suivante, **Définir un nouveau site de succursale**, procédez de l’une des façons suivantes :
    
    1.  Cliquez sur **Ville**, puis entrez le nom de la ville du site de succursale.
    
    2.  Cliquez sur **Dép./Région**, puis entrez le nom du département ou de la région où se trouve le site de succursale.
    
    3.  Cliquez sur **Indicatif du pays**, puis saisissez l’indicatfif à deux chiffres de la région/du pays où le site de succursale est basé.

7.  Cliquez sur **Suivant**, puis effectuez l’une des options suivantes :
    
    1.  Si vous utilisez un SBA ou un serveur Lync 2010 sur ce site, assurez-vous d’avoir désactivé la case à cocher **Ouvrir l’Assistant Nouveau Survivable Branch Appliance à la fermeture de cet Assistant**. Cliquez sur **Terminer**.

8.  Pour associer le SBA Lync Server 2010 hérité au pool frontal Lync Server 2013 :
    
    1.  Développez le site de succursale créé.
    
    2.  Cliquez avec le bouton droit sur **Lync Server 2010** puis cliquez sur **Nouveau**.
    
    3.  Cliquez sur **Survivable Branch Appliance…**

9.  Suivez les instructions de l’Assistant qui s’ouvre. Pour obtenir des informations sur les éléments de l’Assistant, reportez-vous à [Définition d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server dans Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).
    
    > [!NOTE]  
    > Un SBA Lync Server 2010 peut uniquement être associé à un magasin de surveillance Lync Server 2010.

10. Si vous n’utilisez pas de SBA ou de serveur sur ce site, désactivez la case à cocher **Ouvrir l’Assistant Nouveau Survivable Branch Appliance à la fermeture de cet Assistant**, puis cliquez sur **Terminer**.

11. Répétez les étapes précédentes pour chaque site de succursale que vous voulez ajouter à la topologie.

