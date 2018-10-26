---
title: Déployer l’outil SEFAUtil
TOCTitle: Déployer l’outil SEFAUtil
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945659(v=OCS.15)
ms:contentKeyID: 53095579
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déployer l’outil SEFAUtil

 

_**Dernière rubrique modifiée :** 2016-12-08_

Pour déployer et gérer la prise d’appel de groupe, vous devez utiliser l’outil du kit de ressources SEFAUtiltool. Cet outil fait partie des outils du kit de ressources Lync Server 2013. Avant de pouvoir installer SEFAUtil, vous devez disposer d’un pool d’applications approuvées dans votre topologie, indiquez SEFAUtil en tant qu’application approuvée et activez la topologie.

> [!IMPORTANT]  
> Le Kit de développement logiciel (SDK) Microsoft Unified Communications Managed API (UCMA) 3.0 Core doit être sur les ordinateurs sur lesquels vous voulez exécuter l’outil SEFAUtil.

Vous pouvez exécuter SEFAUtil dans n’importe quel pool de serveurs frontaux de votre déploiement.

> [!NOTE]  
> Pour plus d’informations sur l’exécution de SEFAUtil, voir l’article du blog Technet, « Comment exécuter SEFAutil ? » à l’adresse <a href="http://go.microsoft.com/fwlink/?linkid=278940" class="uri">http://go.microsoft.com/fwlink/?linkid=278940</a>.

## Pour déployer SEFAUtil

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé, en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires tels que décrits dans [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  L’outil SEFAUtil ne peut être exécuté que sur un ordinateur qui fait partie d’un pool d’applications approuvées. Si nécessaire, définissez un pool d’applications approuvées pour le pool de serveurs frontaux sur lequel vous allez exécuter SEFAUtil. Sur la ligne de commande, exécutez la commande suivante :
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  Définissez l’outil SEFAUtil en tant qu’application approuvée. Sur la ligne de commande, exécutez :
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    > [!NOTE]  
    > Vous pouvez utiliser un autre port si nécessaire.

5.  Activez la topologie avec vos modifications. Sur la ligne de commande, exécutez :
    
        Enable-CsTopology

6.  Installez les outils du kit de ressources Lync Server 2013 sur un serveur frontal qui se trouve dans le pool d’applications sécurisées créé à l’étape 3.

7.  Vérifiez que l’outil SEFAUtil s’exécute correctement ainsi :
    
    1.  Exécutez l’outil à partir de l’invite de commande Windows avec des droits d’administrateur pour afficher les paramètres de transfert d’appel d’un utilisateur de votre déploiement.
        
        > [!NOTE]  
        > L’outil se trouve à l’emplacement \Program Files\Microsoft Lync Server 2013\Reskit.    
    2.  Affichez les paramètres de transfert d’appel d’un utilisateur. Sur la ligne de commande, exécutez :
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        Les paramètres de transfert d’appel de l’utilisateur s’afficheront.

