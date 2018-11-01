---
title: Suppression de BackCompatSite
TOCTitle: Suppression de BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204637(v=OCS.15)
ms:contentKeyID: 49296093
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression de BackCompatSite

 

_**Dernière rubrique modifiée :** 2012-09-28_

Une fois tous les pools désactivés et tous les serveurs Edge désinstallés, exécutez l’Assistant Fusion du générateur de topologie pour supprimer **BackCompatSite** .

## Pour supprimer le site BackCompat à partir du générateur de topologie

1.  Ouvrez un déploiement existant à partir du générateur de topologie.

2.  Dans le menu **Actions** , cliquez sur **Fusionner la topologie 2007 R2** .

3.  Cliquez sur **Suivant** pour continuer.

4.  Dans la page **Spécifier la configuration Edge héritée** , vérifiez que la liste des serveurs Edge est vide. Si elle ne l’est pas, utilisez le bouton **Supprimer** pour supprimer tous les serveurs Edge hérités, puis cliquez sur **Suivant** .
    
    ![Assistant Topologie de la fusion, page Spécifier la configuration Edge](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Assistant Topologie de la fusion, page Spécifier la configuration Edge")  

5.  Dans la page **Spécifier le port SIP interne** , cliquez sur **Suivant** .

6.  Dans la page **Résumé** , cliquez sur **Suivant** pour commencer à fusionner les topologies afin de supprimer le site hérité.

7.  Dans la colonne **Statut** , vérifiez que la valeur est **Opération réussie** , puis cliquez sur **Terminer** pour fermer l’Assistant.

8.  Dans le volet de gauche du générateur de topologie, développez BackCompatSite et vérifiez qu’aucun serveur n’est répertorié.

9.  Cliquez avec le bouton droit sur **BackCompatSite** , puis cliquez sur **Supprimer** .

10. Dans le **Générateur de topologie** , sélectionnez le nœud de niveau supérieur **Lync Server** .

11. Dans le menu **Action** , sélectionnez **Publier la topologie** , puis cliquez sur **Suivant** .

12. Une fois que l’**Assistant Publication** a terminé, cliquez sur **Terminer** pour le fermer.

