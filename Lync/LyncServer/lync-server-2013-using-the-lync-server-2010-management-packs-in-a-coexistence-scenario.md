---
title: "Ut. des packs d’admin. de Lync Server 2010 dans un scénario de coexistence"
TOCtitle: "Ut. des packs d’admin. de Lync Server 2010 dans un scénario de coexistence"
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205078(v=OCS.15)
ms:contentKeyID: 49297996
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Utilisation des packs d’administration de Lync Server 2010 dans un scénario de coexistence

 

_**Dernière rubrique modifiée :** 2012-10-22_

De nombreux clients adoptent un programme de déploiement au sein de leur entreprise pendant lequel les utilisateurs sont progressivement migrés de Microsoft Lync Server 2010 vers Lync Server 2013. Les administrateurs de ces sociétés doivent surveiller les deux versions de Lync Server afin que les utilisateurs bénéficient de la meilleure expérience de communication possible. Pour ce scénario, le pack d’administration Lync Server 2013 prend en charge une migration côte à côte avec le pack d’administration Lync Server 2010.

Dans Lync Server 2010, les ordinateurs Lync Server étaient détectés via le document de topologie stocké dans le magasin central de gestion. Dans cette configuration, un unique ordinateur signalait l’existence de tous les autres ordinateurs Lync Server.

Les packs d’administration pour Lync Server 2013 utilisent désormais une détection au niveau de l’ordinateur au lieu du mécanisme de détection centrale qui était utilisé dans Lync Server 2010. Cela signifie que chaque agent System Center se découvre lui-même et signale son existence à System Center Operations Manager. L’utilisation de la détection au niveau de l’ordinateur facilite l’administration de votre infrastructure System Center et permet également la cohabitation de différentes versions des packs d’administration Lync Server (par exemple, packs d’administration pour Lync Server 2010 et packs d’administration pour Lync Server 2013).

Pour prendre en charge cette migration, vous devez tout d’abord mettre à niveau la surveillance Lync Server 2010 existante pour éviter que la couverture ne fasse défaut. Pour ce faire, sélectionnez un ordinateur Lync Server 2010 existant pour gérer le script de détection centrale pour Lync Server 2010 avant de mettre à niveau votre magasin central de gestion vers Lync Server 2013. Il s’agit d’un processus en quatre étapes :

1.  Mettre à niveau les packs d’administration Lync Server 2010 avec la mise à jour cumulative 7.

2.  Indiquer à un ordinateur Lync Server 2010 d’exécuter le script de détection centrale.

3.  Remplacer le candidat de détection centrale dans le pack d’administration Microsoft Lync Server 2010.

4.  Vérifier que le nouveau candidat de détection centrale a été détecté.

## Indiquer à un ordinateur Lync Server 2010 d’exécuter le script de détection centrale

Pour nommer un ordinateur qui n’est pas un serveur de magasin central de gestion (par exemple, un serveur frontal Lync Server) pour gérer la détection centrale, vous devez créer l’entrée de registre suivante sur le serveur qui n’est pas un magasin central de gestion :

HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate

Vous pouvez créer cette clé de registre en procédant ainsi :

1.  Cliquez sur **Démarrer**, puis sur **Exécuter**.

2.  Dans la boîte de dialogue **Exécuter**, tapez **regedit**, puis appuyez sur Entrée.

3.  Dans l’Éditeur du Registre, développez successivement **HKEY\_LOCAL\_MACHINE**, **SOFTWARE**, **Microsoft**, puis **Real-Time Communications**.

4.  Cliquez avec le bouton droit sur **Health**, cliquez sur **Nouveau**, sur **Clé**. Si la clé **Health** n’existe pas, cliquez avec le bouton droit sur **Real-Time Communications**, pointez sur **Nouveau**, puis cliquez sur **Clé**. Une fois la nouvelle clé créée, tapez Health, et appuyez sur Entrée.
    
    Une fois la nouvelle clé créée, tapez **CentralDiscoveryCandidate** et appuyez sur Entrée pour renommer la clé.

L’application de cette modification peut prendre plusieurs heures. Pour que cette modification soit appliquée immédiatement, arrêtez et redémarrez le service de l’agent d’intégrité. Pour ce faire, procédez ainsi sur l’ordinateur Lync Server 2010 :

1.  Cliquez sur **Démarrer**, sur **Tous les programmes**, puis sur **Accessoires**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.

2.  Dans la fenêtre de console, tapez la commande suivante, puis appuyez sur Entrée :
    
        Net stop HealthService

3.  Un message s’affiche indiquant que « Le service System Center Management est en cours d’arrêt », suivi par un second message qui vous indique que le service est arrêté. Une fois le service arrêté, vous pouvez le redémarrer en tapant la commande suivante et en appuyant sur Entrée :
    
        Net start HealthService

## Remplacement du candidat de détection centrale dans le pack d’administration Lync Server 2010

Une fois que vous avez indiqué à un ordinateur Lync Server 2010 de signaler les ordinateurs Lync Server 2010, vous devez informer le pack d’administration Lync Server 2010 de cette modification. Pour ce faire, vous devez créer un remplacement dans le pack d’administration. Pour cela, effectuez la procédure suivante :

1.  Dans la console Operations Manager, cliquez sur **Création**.

2.  Sous l’onglet Création, développez **Objets du pack d’administration**, cliquez sur **Détections d’objets**, puis sur **Étendue**.

3.  Dans la boîte de dialogue **Étendre les objets du pack d’administration**, sélectionnez l’élément avec le **Candidat de détection LS** cible, puis cliquez sur **OK**. Notez que le candidat de détection LS s’affiche uniquement si vous avez installé le pack d’administration Lync Server 2010.

4.  Dans la console Operations Manager, cliquez avec le bouton droit sur **Candidat de détection LS**, pointez sur **Remplacements**, sur **Remplacer la détection d’objets**, puis cliquez sur **Pour tous les objets de la classe : candidat de détection LS**.

5.  Dans la boîte de dialogue **Propriétés du remplacement**, cochez la case **Remplacer** en regard du paramètre **Fqdn nœud observateur détection centrale**. Tapez le nom de domaine complet de l’ordinateur Lync Server 2010 dans les zones **Valeur de remplacement** et **Valeur effective**. Cochez la case **Appliqué**, puis cliquez sur **OK**.

Une fois le remplacement créé, vous devez redémarrer le service de contrôle d’intégrité sur le serveur d’administration racine. Pour redémarrer le service, procédez ainsi sur le serveur d’administration racine :

1.  Cliquez sur **Démarrer**, sur **Tous les programmes**, puis sur **Accessoires**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.

2.  Dans la fenêtre de console, tapez la commande suivante, puis appuyez sur Entrée :
    
        Net stop HealthService

3.  Un message s’affiche indiquant que « Le service System Center Management est en cours d’arrêt », suivi par un second message qui vous indique que le service est arrêté. Une fois le service arrêté, vous pouvez le redémarrer en tapant la commande suivante et en appuyant sur Entrée :
    
        Net start HealthService

## Vérification que le nouveau candidat de détection centrale a été détecté

Avant de mettre à niveau le magasin central d’administration, vous devez vous assurer que le nouveau candidat de détection centrale a été détecté par le pack d’administration Lync Server 2010. Pour ce faire, ouvrez la console Operations Manager, puis cliquez sur Analyse. Sous l’onglet Analyse, développez **Intégrité Microsoft Lync Server 2010**, **Découverte de la topologie**, puis cliquez sur **Affichage des états de détection**. Vérifiez qu’une ligne de l’affichage comprend un **Chemin** qui répertorie le nom de domaine complet du candidat de détection central. Vérifiez également que l’état de l’ordinateur est **Sain**.

