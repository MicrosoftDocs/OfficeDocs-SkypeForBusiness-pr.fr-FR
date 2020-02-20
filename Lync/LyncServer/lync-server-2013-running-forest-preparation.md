---
title: 'Lync Server 2013 : exécution de la préparation de la forêt'
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
ms.openlocfilehash: df862c99d05ea27a305a9965e9026065ecfe7792
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="running-forest-preparation-for-lync-server-2013"></a>Exécution de la préparation de la forêt pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-29_

Vous pouvez utiliser le programme d’installation ou les applets de commande Lync Server Management Shell pour préparer la forêt. L’applet de commande qui prépare la forêt est **Enable-CsAdForest**.

Après avoir préparé la forêt, vous devez vérifier que les paramètres globaux ont été répliqués avant de préparer le domaine.

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a>Pour utiliser le programme d’installation afin de préparer la forêt

1.  Ouvrez une session sur un ordinateur lié à un domaine en tant que membre du groupe Administrateurs d’entreprise pour le domaine racine de la forêt.

2.  À partir du dossier ou du support d’installation de Lync Server 2013, exécutez Setup. exe pour démarrer l’Assistant déploiement.

3.  Cliquez sur **Préparer Active Directory**, puis attendez que l’état du déploiement soit déterminé.

4.  À l’**Étape 3 : Préparer la forêt actuelle**, cliquez sur **Exécuter**.

5.  Dans la page **Préparer la forêt**, cliquez sur **Suivant**.
    
    <div>
    

    > [!NOTE]  
    > La préparation de la forêt vous permet de choisir où placer les groupes universels pour Lync Server 2013. Choisissez un emplacement cohérent avec les conditions requises de votre organisation.

    
    </div>

6.  Sur la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**.

7.  Sous la colonne **action** , développez préparation de la **forêt**, ** \<recherchez\> ** un résultat d’exécution réussie à la fin de chaque tâche pour vérifier que la préparation de la forêt s’est correctement effectuée, fermez le journal, puis cliquez sur **Terminer**.

8.  Attendez que la réplication Active Directory soit terminée ou forcez la réplication sur tous les contrôleurs de domaine répertoriés dans le composant logiciel enfichable **Sites et services Active Directory** pour le contrôleur du domaine racine de la forêt, avant d’exécuter l’opération de préparation d’un domaine. Forcez la réplication entre les contrôleurs de domaine sur tous les sites Active Directory pour faire en sorte que la réplication au sein de ces sites se produise en quelques minutes.

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a>Pour préparer la forêt à l’aide d’applets de commande

1.  Ouvrez une session sur un ordinateur qui est associé à un domaine en tant que membre du groupe Administrateurs du domaine dans le domaine racine de la forêt.

2.  Installez les composants principaux de Lync Server comme suit :
    
    1.  À partir du dossier ou du support d’installation de Lync Server 2013, exécutez Setup. exe pour démarrer l’Assistant Déploiement de Lync Server.
    
    2.  Si le système vous invite à installer le package redistribuable Microsoft Visual C++, cliquez sur **Oui**.
    
    3.  La boîte de dialogue Configuration de Lync Server 2013 vous invite à indiquer un emplacement d’installation des fichiers Lync Server. Choisissez l’emplacement par défaut ou cliquez sur **Parcourir** pour accéder à un emplacement de votre choix, puis cliquez sur **Installer**.
    
    4.  Dans la page Contrat de licence, activez la case à cocher **J’accepte les termes du contrat de licence**, puis cliquez sur **OK**. Le programme d’installation installe les composants principaux de Lync Server 2013.

3.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

4.  Générer
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    Par exemple :
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    Si vous omettez le paramètre GroupDomain, le domaine local est utilisé par défaut. Si les groupes universels ont été créés dans un domaine qui n’est pas le domaine par défaut, vous devez spécifier explicitement le paramètre GroupDomain.

5.  Attendez que la réplication Active Directory soit terminée ou forcez la réplication sur tous les contrôleurs de domaine répertoriés dans le composant logiciel enfichable **Sites et services Active Directory** pour le contrôleur du domaine racine de la forêt, avant d’exécuter l’opération de préparation d’un domaine.

6.  Vérifiez que la préparation de la forêt a été exécutée avec succès. Exécutez :
    
        Get-CsAdForest 
    
    Cette applet de commande renvoie une **valeur\_de\_LC\_FORESTSETTINGS State Ready** si la préparation de la forêt a réussi.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Utilisation d’applets de commande pour inverser la préparation de la forêt pour Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[Préparation de la forêt pour Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

