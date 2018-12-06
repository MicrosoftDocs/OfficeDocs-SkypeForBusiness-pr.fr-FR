---
title: "Lync Server 2013 : Conf. des noms de dom. complets d’une batterie de serv. web"
TOCTitle: Configuration des noms de domaine complets d’une batterie de serveurs web
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg429722(v=OCS.15)
ms:contentKeyID: 49298868
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des noms de domaine complets d’une batterie de serveurs web pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-03-29_

Lorsque vous définissez la configuration du serveur Standard Edition, du pool de serveurs frontaux, du directeur ou du pool de directeurs dans Générateur de topologie, vous configurez un nom de domaine complet des services web externes. Durant le processus de connexion d’un client hébergé sur le serveur Standard Edition ou le pool de serveurs frontaux, les noms de domaine complets des services web configurés sont envoyés via une mise en service intrabande. Si vous devez ajouter ou modifier l’URL des services web externes, utilisez le Générateur de topologie pour configurer ou reconfigurer les services web en suivant la procédure dans cette rubrique.

## Pour configurer le nom de domaine complet du pool externe pour les services web

1.  Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.

2.  Dans l’arborescence de la console du Générateur de topologie, sous **Pools frontaux Standard Edition**, **Pools frontaux Enterprise Edition** et **Directeurs**, cliquez avec le bouton droit sur le nom du pool que vous devez modifier, puis cliquez sur **Modifier les propriétés**.

3.  Dans la section **Services web**, ajoutez ou modifiez le **nom de domaine complet des services web externes**.

4.  Vérifiez et ajustez les **ports d’écoute** pour HTTP et HTTPS. Les valeurs suivantes sont définies par défaut :
    
      - **Ports d’écoute :** HTTP 8080, HTTPS 4443
    
      - **Ports publiés :** HTTP 80, HTTPS 443
    
    Les **ports d’écoute** sont les ports via lesquels les services web externes reçoivent les requêtes du proxy inverse. Les **ports publiés** sont publiés en externe par le proxy inverse et communiqués aux clients durant la mise en service intrabande.

5.  Une fois vos ajouts et mises à jour effectués, cliquez sur **OK** pour continuer.

6.  Cliquez avec le bouton droit sur **Lync Server 2013**, puis cliquez sur **Publier**.
    
    > [!IMPORTANT]  
    > Une fois la publication terminée, un lien vous informant que des opérations supplémentaires doivent être effectuées peut s’afficher. Cliquez sur le lien pour ouvrir la liste des serveurs affectés par les modifications apportées dans le Générateur de topologie qui nécessiteront de ré-exécuter l’Assistant Déploiement de Lync Server sur chaque serveur répertorié pour mettre à jour la configuration pour les composants ajoutés, supprimés ou modifiés.

7.  Répétez ces étapes pour le serveur Standard Edition, le pool de serveurs frontaux, le directeur ou le pool de directeurs dans l‘organisation.

