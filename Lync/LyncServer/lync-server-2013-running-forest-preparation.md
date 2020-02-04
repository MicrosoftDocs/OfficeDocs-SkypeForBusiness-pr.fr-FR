---
title: 'Lync Server 2013 : Exécution de la préparation de la forêt'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running forest preparation
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412732(v=OCS.15)
ms:contentKeyID: 48184991
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 129926afe17f946a2ea32d7c67fdea89fab32a54
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-forest-preparation-for-lync-server-2013"></a>Exécution de la préparation de la forêt pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-29_

Vous pouvez utiliser les applets de applet de configuration ou Lync Server Management Shell pour préparer la forêt. L’applet de cmdlet qui prépare la forêt est **Enable-CsAdForest**.

Après avoir préparé la forêt, vous devez vérifier que les paramètres globaux ont été répliqués avant d’exécuter la préparation du domaine.

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a>Pour préparer la forêt à l’aide du programme d’installation

1.  Ouvrez une session sur un ordinateur qui est joint à un domaine en tant que membre du groupe administrateurs d’entreprise pour le domaine racine de la forêt.

2.  À partir du dossier d’installation ou du média de Lync Server 2013, exécutez Setup. exe pour démarrer l’Assistant déploiement.

3.  Cliquez sur **Préparer Active Directory**, puis attendez que l’état du déploiement soit déterminé.

4.  À l' **étape 3 : préparer la forêt actuelle**, cliquez sur **exécuter**.

5.  Sur la page **préparer la forêt** , cliquez sur **suivant**.
    
    <div>
    

    > [!NOTE]  
    > La préparation de la forêt vous permet de choisir où placer les groupes universels pour Lync Server 2013. Sélectionnez un emplacement conforme aux besoins de votre organisation.

    
    </div>

6.  Dans la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**.

7.  Sous la colonne **action** , développez **Forest PREP**, recherchez un ** \<résultat\> ** d’exécution réussie à la fin de chaque tâche pour vérifier que la préparation de la forêt s’est déroulée correctement, fermez le journal, puis cliquez sur **Terminer**.

8.  Attendez la fin de la réplication Active Directory ou forcez la réplication vers tous les contrôleurs de domaine répertoriés dans le composant logiciel enfichable **sites et services Active Directory** pour le contrôleur de domaine racine de la forêt avant d’exécuter la préparation du domaine. Forcez la réplication entre les contrôleurs de domaine dans tous les sites Active Directory pour que la réplication au sein des sites se produise en quelques minutes.

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a>Pour utiliser des applets de cmdlet pour préparer la forêt

1.  Ouvrez une session sur un ordinateur qui est joint à un domaine en tant que membre du groupe Domain Admins dans le domaine racine de la forêt.

2.  Installez les composants principaux de Lync Server comme suit :
    
    1.  À partir du dossier d’installation ou du média de Lync Server 2013, exécutez Setup. exe pour démarrer l’Assistant Déploiement de Lync Server.
    
    2.  Si vous êtes invité à installer le package redistribuable Microsoft Visual C++, cliquez sur **Oui**.
    
    3.  La boîte de dialogue de configuration de Lync Server 2013 vous invite à entrer un emplacement d’installation des fichiers du serveur Lync. Choisissez l’emplacement par défaut ou **Naviguez** jusqu’à l’emplacement de votre choix, puis cliquez sur **installer**.
    
    4.  Sur la page contrat de licence, activez la case à cocher **J’accepte les termes du contrat de licence**, puis cliquez sur **OK**. Le programme d’installation installe les composants principaux de Lync Server 2013.

3.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

4.  Exécutez :
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    Par exemple :
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    Si vous ne spécifiez pas le paramètre GroupDomain, la valeur par défaut est le domaine local. Si des groupes universels ont été créés auparavant dans un domaine qui n’est pas le domaine par défaut, vous devez spécifier le paramètre GroupDomain explicitement.

5.  Attendez la fin de la réplication Active Directory ou forcez la réplication vers tous les contrôleurs de domaine répertoriés dans le composant logiciel enfichable **sites et services Active Directory** pour le contrôleur de domaine racine de la forêt avant d’exécuter la préparation du domaine.

6.  Vérifiez que la préparation de la forêt a réussi. Exécutez :
    
        Get-CsAdForest 
    
    Cette applet de cmdlet renvoie une valeur de la **LC\_\_FORESTSETTINGS état\_Ready** si la préparation de la forêt a réussi.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Utilisation des commandes d’applet pour inverser la préparation d’une forêt pour Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[Préparation de la forêt pour Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

