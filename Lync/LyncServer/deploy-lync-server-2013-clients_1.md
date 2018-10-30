---
title: Déploiement des clients Lync Server 2013
TOCTitle: Déploiement des clients Lync Server 2013
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204883(v=OCS.15)
ms:contentKeyID: 49297191
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déploiement des clients Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-19_

Après avoir fait migrer des utilisateurs vers Lync Server 2013, procédez comme suit :

1.  Utilisez le filtre de version du client sur le nouveau serveur Lync Server 2013 pour autoriser uniquement les clients, sur lesquels les mises à jour les plus récentes sont installées, à se connecter.

2.  Le cas échéant, configurez les paramètres de stratégie de groupe nécessaires pour le démarrage des clients. Pour plus d’informations, reportez-vous à [Configuration des stratégies d’amorçage clientes dans Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) dans la documentation de déploiement. La configuration de ces paramètres est uniquement nécessaire si vous souhaitez modifier les stratégies de démarrage des clients existantes ou si vous souhaitez en définir de nouvelles. Si vous n’envisagez pas de configurer des stratégies de démarrage des clients, ou si vous souhaitez que celles héritées restent en vigueur, aucune action n’est nécessaire.

3.  Configurez d’autres stratégies utilisateur et client pour des utilisateurs spécifiques ou des groupes d’utilisateurs à l’aide du Panneau de configuration Lync Server 2013, de Lync Server 2013 Management Shell ou des deux. Pour plus d’informations, reportez-vous à [Paramètres nouveaux et modifiés pour Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) et dans la documentation de planification.

4.  Déployez la dernière version des clients Lync Server 2013 avec les dernières mises à jour cumulatives. Pour plus d’informations, reportez-vous à [Déploiement des clients et appareils dans Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) dans la documentation de déploiement.

5.  (Facultatif) Si votre organisation a besoin du mode de confidentialité de la présence avancée Lync Server 2013, une fois la migration terminée, définissez une règle de stratégie de version du client pour empêcher les versions précédentes du client de se connecter. Ensuite, activez le mode de confidentialité de la présence avancée.
    
    > [!IMPORTANT]  
    > N’activez pas le mode de confidentialité de la présence avancée Lync 2013 tant que tous les utilisateurs d’un pool serveur donné n’ont pas installé les versions du client les plus récentes.
