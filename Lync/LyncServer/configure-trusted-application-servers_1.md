---
title: Configuration des serveurs d’application approuvés
TOCTitle: Configuration des serveurs d’application approuvés
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204865(v=OCS.15)
ms:contentKeyID: 49297085
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des serveurs d’application approuvés

 

_**Dernière rubrique modifiée :** 2012-10-04_

Dans un environnement mixte, si vous créez un serveur d’applications approuvées après avoir fusionné la topologie Office Communications Server héritée avec Lync Server 2013, puis définissez un nouveau serveur d’applications approuvées à l’aide du générateur de topologie, vous devez définir le pool du tronçon suivant en tant que pool Lync Server 2013. Dans un environnement fusionné, le pool Office Communications Server hérité et le pool Lync Server 2013 s’affichent dans la liste déroulante. La sélection du pool hérité *n’est pas* prise en charge.

## Pour sélectionner Lync Server 2013 comme tronçon suivant lors de la création d’un serveur d’applications approuvées

1.  Ouvrez une topologie existante dans le générateur de topologie.

2.  Dans le volet gauche, cliquez avec le bouton droit sur **Serveurs d’applications approuvées** , puis cliquez sur **Nouveau pool d’applications approuvées** .

3.  Entrez le **Nom de domaine complet (FQDN) du pool** de l’application approuvée et indiquez s’il s’agit d’un déploiement d’un seul serveur ou de plusieurs serveurs.

4.  Cliquez sur **Suivant** .

5.  Dans la page **Sélectionner le tronçon suivant** , sélectionnez, dans la liste, le pool de serveurs frontaux Lync Server 2013.
    
    ![Boîte de dialogue Définir un nouveau pool d’applications approuvées](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Boîte de dialogue Définir un nouveau pool d’applications approuvées")  

6.  Cliquez sur **Terminer** .

7.  Sélectionnez le nœud supérieur **Lync Server** puis, dans le volet **Actions** , sélectionnez **Publier** .

8.  Vérifiez si le **Pool d’applications approuvées** a été correctement créé et s’il est associé au pool frontal approprié.

