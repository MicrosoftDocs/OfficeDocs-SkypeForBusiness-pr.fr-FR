---
title: Téléchargement de la topologie à partir d’un déploiement existant
TOCTitle: Téléchargement de la topologie à partir d’un déploiement existant
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49891577
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Téléchargement de la topologie à partir d’un déploiement existant

 

_**Dernière rubrique modifiée :** 2012-09-29_

Lorsque vous créez un pool Lync Server 2013, vous utilisez le magasin central de gestion associé à Lync Server 2010. Lorsque vous démarrez le générateur de topologie pour la première fois et lors des sessions de modification ultérieures, le système vous invite à spécifier l’emplacement où le générateur de topologie doit charger le document de configuration actuel. Une topologie Lync Server 2010 étant déjà définie et le magasin central de gestion établi, vous devez choisir de télécharger une topologie à partir d’un déploiement existant. Le générateur de topologie lit la base de données et récupère la définition actuelle.

**Pour télécharger une topologie à partir d’un déploiement existant**

1.  Ouvrez l’**Assistant Déploiement Lync Server** .

2.  À partir de la page **Lync Server 2013 – Assistant Déploiement** , cliquez sur **Installer les outils d’administration** .

3.  Lancez le générateur de topologie : cliquez sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013** , puis **Générateur de topologie Lync Server**.

4.  Sélectionnez **Télécharger une topologie à partir d’un déploiement existant**.
    
    ![Paramètres du Générateur de topologie de l’Assistant Déploiement](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Paramètres du Générateur de topologie de l’Assistant Déploiement")

5.  Choisissez un nom de fichier et enregistrez la topologie avec le type de fichier .tbxml par défaut.

6.  Développez le nœud Lync Server, comme indiqué, pour découvrir les différents rôles de serveur dans le déploiement.
    
    ![Propriétés générales du rôle serveur du Générateur de topologie](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Propriétés générales du rôle serveur du Générateur de topologie")

