---
title: Configuration des enregistrements DNS pour le déploiement du pool pilote
TOCTitle: Configuration des enregistrements DNS pour le déploiement du pool pilote
ms:assetid: 5c7a6e10-e1e9-4479-9bf9-d4a3e2e09ff0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688072(v=OCS.15)
ms:contentKeyID: 49891367
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des enregistrements DNS pour le déploiement du pool pilote

 

_**Dernière rubrique modifiée :** 2012-09-24_

Avant de déployer le pool pilote Lync Server 2013, vous devez mettre à jour les entrées d’hôte DNS (A) pour le pool pilote. Pour réussir cette procédure, vous devez être connecté au serveur ou au domaine au minimum en tant que membre du groupe Admins du domaine ou du groupe DnsAdmins.

**Pour configurer les enregistrements d’hôte DNS (A)**

1.  Sur le serveur DNS, cliquez sur **Démarrer** , sur **Outils d’administration** , puis sur **DNS** .

2.  Dans l’arborescence de la console de votre domaine, développez **Transférer les zones de recherche** , puis cliquez avec le bouton droit sur le domaine dans lequel Lync Server 2013 sera installé.

3.  Cliquez sur **Nouvel hôte (A ou AAAA)** .

4.  Cliquez sur **Nom** , tapez le nom d’hôte du pool (le nom de domaine est présumé à partir de la zone dans laquelle est défini l’enregistrement, il est inutile de l’entrer comme partie de l’enregistrement A).

5.  Cliquez sur **Adresse IP** , puis tapez l’adresse IP du pool de serveurs frontaux.

6.  Cliquez sur **Ajouter un hôte** , puis sur **OK** .

7.  Lorsque vous avez terminé, cliquez sur **Terminé** .

