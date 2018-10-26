---
title: Configuration des serveurs d’applications approuvées
TOCTitle: Configuration des serveurs d’applications approuvées
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204735(v=OCS.15)
ms:contentKeyID: 49296488
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des serveurs d’applications approuvées

 

_**Dernière rubrique modifiée :** 2014-11-05_

Si vous créez un serveur d’applications approuvées dans un environnement mixte, vous devez définir le pool du tronçon suivant en tant que pool Lync Server 2013. Dans un environnement mixte, le pool Lync Server 2010 hérité et le pool Lync Server 2013 figurent tous deux dans la liste déroulante. La sélection du pool hérité n’est pas prise en charge.

**Sélectionner Lync Server 2013 comme tronçon suivant lors de la création d’un serveur d’applications approuvées**

1.  Ouvrez le générateur de topologie.

2.  Dans le volet gauche, cliquez avec le bouton droit sur **Serveurs d’applications approuvées** , puis cliquez sur **Nouveau pool d’applications approuvées** .

3.  Entrez le **Nom de domaine complet du pool** de l’application approuvée et indiquez s’il s’agira d’un serveur unique ou d’un serveur multiple.

4.  Cliquez sur **Suivant** .

5.  Dans la page **Sélectionner le tronçon suivant** , sélectionnez, dans la liste, le pool de serveurs frontaux Lync Server 2013.

6.  Cliquez sur **Terminer** .

7.  Sélectionnez le nœud supérieur **Lync Server** et dans le menu **Action** , sélectionnez **Publier** .
    
    Le **Pool d’applications approuvées** doit avoir été créé avec succès et être associé au pool frontal correct.

