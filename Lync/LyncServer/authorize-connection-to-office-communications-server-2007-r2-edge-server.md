---
title: "Autor. de la connexion au serveur Edge Office Communications Server 2007 R2"
TOCtitle: "Autor. de la connexion au serveur Edge Office Communications Server 2007 R2"
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204702(v=OCS.15)
ms:contentKeyID: 49296346
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Autorisation de la connexion au serveur Edge Office Communications Server 2007 R2

 

_**Dernière rubrique modifiée :** 2012-09-28_

Pour chaque serveur frontal Lync Server 2013 ou serveur Standard Edition de votre pool pilote, vous devez mettre à jour la liste des serveurs internes autorisés à se connecter au serveur Edge Office Communications Server 2007 R2. Sans ces mises à jour, les conférences audio/vidéo (A/V) externes ne peuvent pas fonctionner pour les participants qui utilisent un serveur Edge hérité.

## Pour autoriser la connexion au serveur Edge Office Communications Server 2007 R2

1.  À partir du serveur Edge Office Communications Server 2007 R2, dans le groupe **Outils d’administration** , ouvrez le composant logiciel enfichable **Gestion de l’ordinateur** .

2.  Dans l’arborescence de la console, développez **Services et applications** .

3.  Cliquez avec le bouton droit sur **Office Communications Server 2007 R2**, puis cliquez sur **Propriétés** .

4.  Cliquez sur l’onglet **Interne** .

5.  Sous **Ajouter un serveur** , cliquez sur **Ajouter** .

6.  Dans la boîte de dialogue **Ajouter Office Communications Server**, entrez les informations appropriées :
    
      - Indiquez le nom de domaine complet (FQDN) de chaque serveur frontal Lync Server 2013 ou serveur Standard Edition et du pool Lync Server 2013.
    
      - Spécifiez le nom de domaine complet (FQDN) du directeur Lync Server 2013 si vous avez configuré un itinéraire statique sur le pool qui spécifie l’ordinateur du tronçon suivant par son nom de domaine complet.

7.  Après avoir ajouté une entrée pour chaque Lync Server 2013, serveur frontal, serveur Standard Edition, pool et directeur, cliquez sur **Appliquer**, puis sur **OK** pour fermer la page Propriétés.

