---
title: Mise à jour des environnements SRV DNS
TOCTitle: Mise à jour des environnements SRV DNS
ms:assetid: 9542b91a-108c-4980-89ec-634905cbbf26
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688139(v=OCS.15)
ms:contentKeyID: 49891451
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Mise à jour des environnements SRV DNS

 

_**Dernière rubrique modifiée :** 2012-09-29_

Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.

Cette rubrique explique comment mettre à jour les enregistrements DNS (Domain Name System) après une migration vers Lync Server 2013. Après le déplacement de tous les utilisateurs vers Lync Server 2013, mais avant la mise hors service du pool ou directeur Lync Server 2010 hérité, vous devez mettre à jour les enregistrements DNS SRV dans votre système DNS interne pour chaque domaine SIP. Cette procédure suppose que votre serveur DNS interne comporte des zones pour vos domaines d’utilisateurs SIP.

**Pour configurer un enregistrement DNS SRV**

1.  Sur le serveur DNS, cliquez sur **Démarrer** , sur **Outils d’administration** , puis sur **DNS** .

2.  Dans l’arborescence de la console pour votre domaine SIP, développez **Zones de recherche directes** , développez le domaine SIP dans lequel Lync Server 2013 est installé, puis accédez au paramètre  **\_tcp**.

3.  Dans le volet droit, cliquez avec le bouton droit sur **\_sipinternaltls**, puis sélectionnez **Propriétés**.

4.  Dans **Hôte offrant ce service** , mettez à jour le nom de domaine complet de l’hôte de sorte qu’il pointe vers le pool Lync Server 2013.

5.  Cliquez sur **OK** .

**Pour vérifier que le nom de domaine complet du pool frontal ou du serveur Standard Edition peut être résolu**

1.  Ouvrez une session sur un ordinateur client du domaine.

2.  Cliquez sur **Démarrer** , puis sur **Exécuter** .

3.  Dans la zone **Ouvrir** , tapez **cmd** , puis cliquez sur **OK** .

4.  Dans l’invite de commandes, tapez **nslookup** *\<nom de domaine complet du pool frontal\>* ou *\<nom de domaine complet du serveur Standard Edition\>* et appuyez sur Entrée.

5.  Vérifiez que vous recevez une réponse résolue en adresse IP appropriée pour le nom de domaine complet.

