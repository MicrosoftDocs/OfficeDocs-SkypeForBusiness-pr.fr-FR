---
title: Configuration des enregistrements DNS pour le déploiement d’un pool pilote
TOCTitle: Configuration des enregistrements DNS pour le déploiement d’un pool pilote
ms:assetid: eb421bad-4bf1-4837-a077-7795094692d9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721921(v=OCS.15)
ms:contentKeyID: 49891595
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des enregistrements DNS pour le déploiement d’un pool pilote

 

_**Dernière rubrique modifiée :** 2012-09-29_

Avant de pouvoir déployer le premier pool Lync Server 2013, vous devez mettre à jour ses entrées d’hôte DNS (A). Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.

**Pour configurer les enregistrements d’hôte DNS (A)**

1.  Sur le serveur DNS, cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.

2.  Dans l’arborescence de la console de votre domaine, développez **Transférer les zones de recherche**, puis cliquez avec le bouton droit sur le domaine dans lequel Lync Server 2013 sera installé.

3.  Cliquez sur **Nouvel hôte (A ou AAAA)**.

4.  Cliquez sur **Nom**, tapez le nom d’hôte du pool Lync Server 2013 (le nom de domaine est supposé à partir de la zone dans laquelle l’enregistrement est défini, et ne doit pas nécessairement être entré comme faisant partie de l’enregistrement A).

5.  Cliquez sur **Adresse IP**, puis tapez l’adresse IP du pool de serveurs frontaux.

6.  Cliquez sur **Ajouter un hôte**, puis sur **OK**.

7.  Lorsque vous avez terminé, cliquez sur **Terminé**.

