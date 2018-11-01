﻿---
title: 'Lync Server 2013 : Exécution de la préparation de la forêt'
TOCTitle: Exécution de la préparation de la forêt
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412732(v=OCS.15)
ms:contentKeyID: 49298365
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exécution de la préparation de la forêt pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-29_

Vous pouvez utiliser le programme d’installation ou des applets de commande Lync Server Management Shell pour préparer la forêt. L’applet de commande qui prépare la forêt est **Enable-CsAdForest**.

Après avoir préparé la forêt, vous devez vérifier que les paramètres globaux ont été répliqués avant de préparer le domaine.

## Pour utiliser le programme d’installation afin de préparer la forêt

1.  Ouvrez une session sur un ordinateur lié à un domaine en tant que membre du groupe Administrateurs d’entreprise pour le domaine racine de la forêt.

2.  À partir du dossier ou du support d’installation de Lync Server 2013, exécutez le fichier Setup.exe pour démarrer l’Assistant Déploiement.

3.  Cliquez sur **Préparer Active Directory** , puis attendez que l’état du déploiement soit déterminé.

4.  À l’**Étape 3 : Préparer la forêt actuelle** , cliquez sur **Exécuter** .

5.  Dans la page **Préparer la forêt** , cliquez sur **Suivant** .
    
    > [!NOTE]  
    > La préparation de la forêt vous permet de choisir l’emplacement des groupes universels de Lync Server 2013. Sélectionnez un emplacement cohérent avec les besoins de votre organisation.

6.  Dans la page **Exécution de commandes** , recherchez **Statut de la tâche : Terminée** , puis cliquez sur **Afficher le journal** .

7.  Sous la colonne **Action** , développez **Préparation de la forêt** , recherchez le résultat d’exécution **\<Opération réussie\>** à la fin de chaque tâche afin de vérifier que la préparation de la forêt a abouti, fermez le journal, puis cliquez sur **Terminer** .

8.  Attendez que la réplication Active Directory soit terminée ou forcez la réplication sur tous les contrôleurs de domaine répertoriés dans le composant logiciel enfichable **Sites et services Active Directory** pour le contrôleur du domaine racine de la forêt, avant d’exécuter l’opération de préparation d’un domaine. Forcez la réplication entre les contrôleurs de domaine sur tous les sites Active Directory pour faire en sorte que la réplication au sein de ces sites se produise en quelques minutes.

## Pour préparer la forêt à l’aide d’applets de commande

1.  Ouvrez une session sur un ordinateur associé à un domaine en tant que membre du groupe Administrateurs du domaine dans le domaine racine de la forêt.

2.  Installez les composants principaux de Lync Server en procédant comme suit :
    
    1.  À partir du dossier ou du support d’installation de Lync Server 2013, exécutez Setup.exe pour démarrer l’Assistant Déploiement de Lync Server.
    
    2.  Si vous êtes invité à installer le package redistribuable Microsoft Visual C++, cliquez sur **Oui** .
    
    3.  La boîte de dialogue Installation de Lync Server 2013 vous invite à indiquer l’emplacement des fichiers Lync Server. Choisissez l’emplacement par défaut ou cliquez sur **Parcourir** pour accéder à un emplacement de votre choix, puis cliquez sur **Installer** .
    
    4.  Dans la page Contrat de licence, activez la case à cocher **J’accepte les termes du contrat de licence** , puis cliquez sur **OK** . Le programme d’installation installe les composants principaux de Lync Server 2013.

3.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

4.  Exécutez :
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    Exemple :
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    Si vous omettez le paramètre GroupDomain, le domaine local est utilisé par défaut. Si les groupes universels ont été créés dans un domaine qui n’est pas le domaine par défaut, vous devez spécifier explicitement le paramètre GroupDomain.

5.  Attendez que la réplication Active Directory soit terminée ou forcez la réplication sur tous les contrôleurs de domaine répertoriés dans le composant logiciel enfichable **Sites et services Active Directory** pour le contrôleur du domaine racine de la forêt, avant d’exécuter l’opération de préparation d’un domaine.

6.  Vérifiez que la préparation de la forêt a été exécutée avec succès. Exécutez :
    
        Get-CsAdForest 
    
    Cette applet de commande renvoie la valeur **LC\_FORESTSETTINGS\_STATE\_READY** si la forêt a été préparée correctement.

## Voir aussi

#### Tâches

[Utilisation des commandes d’applet pour inverser la préparation d’une forêt pour Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  

#### Autres ressources

[Préparation de la forêt pour Lync Server 2013](lync-server-2013-preparing-the-forest.md)

