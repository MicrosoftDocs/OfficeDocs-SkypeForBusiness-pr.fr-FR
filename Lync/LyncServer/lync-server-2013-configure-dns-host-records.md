---
title: 'Lync Server 2013 : Configuration des enregistrements hôte DNS'
TOCTitle: Configuration des enregistrements hôte DNS
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398593(v=OCS.15)
ms:contentKeyID: 49297803
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des enregistrements hôte DNS pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-01_

Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine au moins en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.

## Pour configurer les enregistrements d’hôte DNS (A)

1.  Sur le serveur DNS, cliquez sur **Démarrer** , sur **Outils d’administration** , puis sur **DNS** .

2.  Dans l’arborescence de la console de votre domaine, développez **Transférer les zones de recherche** , puis cliquez avec le bouton droit sur le domaine dans lequel Lync Server 2013 sera installé.

3.  Cliquez sur **Nouvel hôte (A ou AAAA)** .

4.  Cliquez sur **Nom** , tapez le nom d’hôte du pool (le nom de domaine est présumé à partir de la zone dans laquelle est défini l’enregistrement, il est inutile de l’entrer comme partie de l’enregistrement A).

5.  Cliquez sur **Adresse IP** et tapez l’adresse IP virtuelle (VIP) du programme d’équilibrage de la charge pour le pool de serveurs frontaux.
    
    > [!IMPORTANT]  
    > Dans les déploiements qui utilisent un pool directeur, les enregistrements hôtes (A) pour les URL simples doivent pointer sur l’adresse IP virtuelle du programme d’équilibrage de la charge du directeur.    
    > [!NOTE]  
    > Si vous déployez un seul serveur Enterprise Edition Server connecté à la topologie sans programme d’équilibrage de la charge, ou si vous déployez un serveur Standard Edition, tapez l’adresse IP du serveur Enterprise Edition Server, Standard Edition Server ou du directeur. L’utilisation d’un programme d’équilibrage de la charge est nécessaire si vous déployez plusieurs serveurs Enterprise Edition Server ou directeur dans un pool. Les programmes d’équilibrage de la charge ne sont pas utilisés avec les serveurs Standard Edition.

6.  Cliquez sur **Ajouter un hôte** , puis sur **OK** .

7.  Pour créer un enregistrement A supplémentaire, répétez les étapes 4 et 5.

8.  Lorsque vous avez terminé de créer tous les enregistrements A dont vous avez besoin, cliquez sur **Terminer** .

