---
title: Vérification de l’environnement Office Communications Server 2007 R2
TOCTitle: Vérification de l’environnement Office Communications Server 2007 R2
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49891572
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vérification de l’environnement Office Communications Server 2007 R2

 

_**Dernière rubrique modifiée :** 2012-10-16_

Avant de déployer Lync Server 2013 en coexistence avec Office Communications Server 2007 R2, vous devez vérifier que les services Office Communications Server 2007 R2 sont configurés et démarrés.

**Vérifiez que le pool est démarré à l’aide de l’outil d’administration Office Communications Server 2007 R2**

1.  Ouvrez l’outil d’administration Office Communications Server 2007 R2.

2.  Développez le nœud **Forêt**, développez le nœud **serveur Standard Edition Servers** ou **pools d’entreprise**, puis développez le nom du pool ou du serveur.

3.  Vérifiez que les services sont exécutés sur le serveur Standard Edition ou le pool d’entreprise.
    
    ![Office Communications Server 2007 R2 - Console d’administration](images/JJ204914.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 - Console d’administration")

**Passez en revue les utilisateurs configurés pour le serveur Office Communications Server 2007 R2**

1.  Ouvrez l’outil d’administration Office Communications Server 2007 R2.

2.  Développez le nœud **Forêt**, développez le nœud **serveur Standard Edition Servers** ou **pools d’entreprise**, puis développez le nom du pool ou du serveur.

3.  Cliquez sur **Utilisateurs**.

4.  Vérifiez la liste des utilisateurs Office Communications Server 2007 R2.
    
    ![Liste des utilisateurs dans l’outil d’administration OCS](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "Liste des utilisateurs dans l’outil d’administration OCS")

**Vérifiez la configuration de partenaire fédéré XMPP héritée**

1.  À partir du serveur XMPP hérité, naviguez vers l’applet Outils/Services d’administration.

2.  Vérifiez que le service de passerelle XMPP Office Communications Server est démarré.
    
    ![Service de la passerelle XMPP d’Office Communications Server](images/JJ205231.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Service de la passerelle XMPP d’Office Communications Server")

