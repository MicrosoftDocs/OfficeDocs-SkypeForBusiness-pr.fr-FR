---
title: "Lync Server 2013 : Déf. d’un SBA ou d’un SBS"
TOCTitle: Définition d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398280(v=OCS.15)
ms:contentKeyID: 49296471
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-07_

Effectuez cette procédure sur le site central si vous n’avez pas défini le Survivable Branch Appliance ou le serveur Survivable Branch Server lorsque vous l’avez ajouté à votre topologie.

## Pour définir un Survivable Branch Appliance ou un serveur Survivable Branch Server

1.  Cliquez sur **Démarrer** , sur **Tous les programmes** , sur **Microsoft Lync Server 2013**, puis sur **Lync ServerGénérateur de topologie**.

2.  Dans l’arborescence de la console, développez le site central, développez **Sites de succursale** , puis développez le nom du site de succursale où vous souhaitez déployer le Survivable Branch Appliance ou le serveur Survivable Branch Server.

3.  Cliquez avec le bouton droit sur **serveurs Survivable Branch Appliance**, puis sur **Nouveau Survivable Branch Appliance**.
    
    > [!IMPORTANT]  
    > <strong>serveurs Survivable Branch Appliance</strong> est l’endroit où vous définissez les serveurs Survivable Branch Server et les serveurs Survivable Branch Appliance.

4.  Dans la boîte de dialogue **Définir Survivable Branch Appliance**, cliquez sur **Nom de domaine complet (FQDN)** , tapez le nom de domaine complet du Survivable Branch Appliance ou du serveur Survivable Branch Server que vous déploierez sur ce site de succursale, puis cliquez sur **Suivant** .
    
    > [!IMPORTANT]  
    > Si vous définissez un Survivable Branch Appliance, le nom que vous entrez dans <strong>Nom de domaine complet (FQDN)</strong> doit être le même que le nom de domaine complet du Survivable Branch Appliance que vous avez affecté à l’attribut <strong>servicePrincipalName</strong> . Pour plus d’informations, reportez-vous à <a href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Ajout d’un Survivable Branch Appliance à Active Directory dans Lync Server 2013</a>.

5.  Cliquez sur **Pool frontal** , cliquez sur le serveur frontal (pool de services d’utilisateurs) du site central auquel ce Survivable Branch Appliance ou ce serveur Survivable Branch Server se connectera, puis cliquez sur **Suivant** .

6.  Cliquez sur **Serveur Edge** , cliquez sur le pool Edge auquel ce Survivable Branch Appliance ou ce serveur Survivable Branch Server se connectera pour que les utilisateurs distants du site de succursale puissent se connecter via le réseau RTC, puis cliquez sur **Suivant** .

7.  Cliquez sur **Adresse IP ou nom de domaine complet de la passerelle** , puis tapez le nom de domaine complet ou l’adresse IP de l’homologue de passerelle auquel le Survivable Branch Appliance ou le serveur Survivable Branch Server est associé pour acheminer les appels RTC entrants ou sortants.
    
    > [!IMPORTANT]  
    > Si vous définissez un Survivable Branch Appliance, il s’agit de la passerelle à laquelle le serveur de médiation dans le Survivable Branch Appliance se connectera pour assurer la connectivité RTC.

8.  Cliquez sur **Port d’écoute pour la passerelle IP/RTC** , puis acceptez le port par défaut.

9.  Dans **Protocole de transport SIP** , cliquez sur le protocole de transport que le Survivable Branch Appliance ou le serveur Survivable Branch Server utilisera, puis cliquez sur **Terminer** .
    
    > [!NOTE]  
    > Pour des raisons de sécurité, nous vous conseillons vivement d’utiliser le protocole TLS (Transport Layer Security). Si vous définissez un Survivable Branch Appliance, reportez-vous à la documentation du fournisseur du Survivable Branch Appliance pour vérifier que votre Survivable Branch Appliance prend en charge le protocole TLS.

10. Dans l’arborescence de la console, cliquez avec le bouton droit sur le nouveau Survivable Branch Appliance ou serveur Survivable Branch Server, cliquez sur **Topologie** , puis sur **Publier** .

**Étape suivante**: [Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server sur un site de succursale avec Lync Server 2013 - tâche de site de succursale](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

