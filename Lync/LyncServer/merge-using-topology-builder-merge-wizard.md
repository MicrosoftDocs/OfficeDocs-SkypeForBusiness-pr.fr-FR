---
title: Fusionner à l’aide de l’Assistant Fusion du générateur de topologie
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61981ae875fef9976377644a9b67f0a329581a90
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763638"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a>Fusionner à l’aide de l’Assistant Fusion du générateur de topologie

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-02_

1.  Téléchargez le déploiement existant à l’aide du générateur de topologie.

2.  Dans le menu **action** , sélectionnez **fusionner Office Communications Server 2007 R2**.

3.  Cliquez sur **Suivant**.

4.  Dans **spécifier le programme d’installation**de Microsoft Edge, cliquez sur **Ajouter**.
    
    ![Assistant Fusion-topologie-définir la page de configuration du bord](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Assistant Fusion-topologie-définir la page de configuration du bord")  

5.  Dans **spécifier le type de bord**, entrez le type de configuration de serveur Edge, puis cliquez sur **suivant**. Cet exemple utilise l’option **serveur Edge unique** .
    
    <div>
    

    > [!IMPORTANT]  
    > Le <STRONG>déploiement Edge étendu</STRONG> n’est pas une configuration prise en charge. Un <STRONG>serveur Edge étendu</STRONG> doit d’abord être converti sur un <STRONG>serveur Edge unique</STRONG> ou un serveur <STRONG>Edge consolidé équilibré</STRONG> .

    
    </div>

6.  Dans **spécifier les paramètres de bord interne** , entrez les informations pertinentes pour le nom de domaine complet (FQDN) du pool de bords et les ports nécessaires, puis cliquez sur **suivant**.
    
    ![Boîte de dialogue spécifier les paramètres de bord interne](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Boîte de dialogue spécifier les paramètres de bord interne")  

7.  Dans **spécifier le bord externe**, entrez les informations de nom de domaine complet pour les conférences Web pour votre serveur Edge.
    
    <div>
    

    > [!IMPORTANT]  
    > Avant de cliquer sur <STRONG>suivant</STRONG>, exécutez l’étape suivante de cette procédure. Il est très important que vous ne manquez pas cette étape.

    
    </div>

8.  Activez la case à cocher **ce pool Edge est utilisé pour la connectivité de Fédération et de messagerie instantanée publique** si vous envisagez d’utiliser l’ancien serveur Office Communications Server 2007 R2 pour la Fédération. Si vous avez déployé plusieurs serveurs Edge, seul l’un d’eux sera activé pour la Fédération. Si vous n’activez pas cette case à cocher et que vous décidez par la suite d’activer la Fédération, vous devez exécuter l’Assistant Fusion du générateur de topologie et publier de nouveau votre topologie.
    
    ![Boîte de dialogue serveur Edge, spécifiez la page de bord externe](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Boîte de dialogue serveur Edge, spécifiez la page de bord externe")  

9.  Dans **spécifier le tronçon suivant**, entrez le nom de domaine complet (FQDN) de l’emplacement du tronçon suivant dans votre environnement. Cliquez sur **Terminer**.
    
    ![Boîte de dialogue serveur Edge, page spécifier le tronçon suivant](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Boîte de dialogue serveur Edge, page spécifier le tronçon suivant")  

10. Dans **spécifier le programme d’installation**de Microsoft Edge, si vous avez ajouté tous vos serveurs Edge Office Communications Server 2007 R2, cliquez sur **suivant**. Si vous avez d’autres serveurs Office Communications Server 2007 R2 à ajouter, répétez cette procédure en commençant à l’étape 4.

11. Dans **spécifier le port SIP interne** , sélectionnez le paramètre par défaut (autrement dit, si vous n’avez pas modifié le port SIP par défaut). Changez le cas échéant si vous n’utilisez pas un port par défaut de 5061, puis cliquez sur **suivant**.

12. En **Résumé**, cliquez sur **suivant** pour commencer à fusionner les topologies.

13. La page de l’Assistant vérifie que la fusion des topologies a abouti.

14. Dans la colonne **État** , assurez-vous que la valeur est **succès**, puis cliquez sur **Terminer**.

15. Dans le volet gauche du générateur de topologie, vous devez maintenant voir le **BackCompatSite**, qui indique que votre environnement Office Communications Server 2007 R2 a été fusionné avec Lync Server 2013.
    
    ![Générateur de topologie présentant une topologie fusionnée](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Générateur de topologie présentant une topologie fusionnée")  

16. Dans le menu **action** , cliquez sur **publier la topologie**, puis sur **suivant**.

17. À la fin de l' **Assistant Publication** , cliquez sur **Terminer**.
    
    <div>
    

    > [!NOTE]  
    > Il est important que vous complétiez la rubrique suivante, <A href="import-policies-and-settings.md">importez les stratégies et paramètres</A>, pour vous assurer que les paramètres de stratégie hérités sont importés dans Lync Server 2013.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

