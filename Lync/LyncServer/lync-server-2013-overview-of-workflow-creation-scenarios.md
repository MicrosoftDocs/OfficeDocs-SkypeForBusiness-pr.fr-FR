---
title: 'Lync Server 2013 : Vue d’ensemble des scénarios de création de flux de travail'
TOCTitle: Vue d’ensemble des scénarios de création de flux de travail
ms:assetid: 05e0c175-0f1a-4bb1-b048-c68584d00649
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204646(v=OCS.15)
ms:contentKeyID: 49296129
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue d’ensemble des scénarios de création de flux de travail dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-17_

Lorsque vous créez des flux de travail, deux scénarios sont possibles :

  - **L’Administrateur crée et configure le flux de travail** — Le membre du rôle CsResponseGroupAdministrator (ou équivalent) crée et active le flux de travail, ainsi que tous les éléments qu’il contient, tels que les groupes d’agents, les files d’attente, les congés et les heures ouvrées, la musique d’attente, etc.

  - **L’administrateur crée le flux de travail et le responsable configure les options** — Le membre du rôle CsResponseGroupAdministrator (ou équivalent) définit l’URI SIP principal et le nom complet, affecte des membres du rôle CsResponseGroupManager, sélectionne une file d’attente et active le flux de travail. Le membre du rôle CsResponseGroupManager peut alors ouvrir une session et modifier la configuration du flux de travail en créant des groupes d’agents. Il affecte également le groupe à la file d’attente, configure le numéro de téléphone, les congés et les heures ouvrées, la musique d’attente, etc.
    
    > [!NOTE]  
    > Lorsque vous voulez créer un flux de travail géré, vous devez créer le flux travail en tant que flux de travail actif. Après avoir enregistré un flux de travail géré et actif, vous pouvez le modifier et le désactiver.
