---
title: 'Lync Server 2013 : exécution de la préparation du schéma'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running schema preparation
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48184911
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12dda05b36406e620c08abac494dceecc7d314d0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201130"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a>Exécution de la préparation du schéma Active Directory dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-29_

Vous pouvez utiliser le programme d’installation ou les applets de commande Lync Server Management Shell pour préparer le schéma Active Directory. L’applet de commande qui étend le schéma Active Directory est **Install-CsAdServerSchema**.

<div>


> [!NOTE]  
> La cmdlet de préparation de schéma (<STRONG>install-CsAdServerSchema</STRONG>) doit accéder au contrôleur de schéma, ce qui nécessite que le service Registre distant soit en cours d’exécution et que la clé de Registre distante soit activée. Si le service Registre distant ne peut pas être activé sur le contrôleur de schéma, vous pouvez exécuter l’applet de commande localement sur le contrôleur de schéma. Pour plus d’informations sur l’accès à distance au registre, consultez l’article 314837 de la base de connaissances Microsoft, « procédure de <A href="https://go.microsoft.com/fwlink/p/?linkid=125769">https://go.microsoft.com/fwlink/p/?linkId=125769</A>gestion de l’accès à distance au registre » à l’adresse.



</div>

Après avoir préparé le schéma, vérifiez manuellement que la partition du schéma a été répliquée avant de procéder à la préparation de la forêt. Pour plus d’informations, consultez [la rubrique vérification de la réplication de schéma Active Directory dans Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a>Pour utiliser le programme d’installation afin de préparer le schéma de la forêt actuelle

1.  Ouvrez une session sur un serveur de la forêt en tant que membre du groupe Administrateurs du schéma et avec les droits d’administrateur sur le maître de schémas.

2.  À partir du dossier ou du support d’installation de Lync Server 2013, exécutez Setup. exe pour démarrer l’Assistant déploiement.

3.  Si le système vous invite à installer le package redistribuable Microsoft Visual C++, cliquez sur **Oui**.

4.  La boîte de dialogue Configuration de Lync Server 2013 vous invite à indiquer un emplacement d’installation des fichiers Lync Server. Choisissez l’emplacement par défaut ou cliquez sur **Parcourir** pour accéder à un emplacement de votre choix, puis cliquez sur **Installer**.

5.  Dans la page Contrat de licence, activez la case à cocher **J’accepte les termes du contrat de licence**, puis cliquez sur **OK**.

6.  Le programme d’installation installe les composants principaux de Lync Server.

7.  Lorsque l’Assistant Déploiement est prêt, cliquez sur **Préparer Active Directory** et attendre le résultat quant à l’état du déploiement.

8.  À l’**Étape 1 : Préparer un schéma**, cliquez sur **Exécuter**.

9.  Dans la page **Préparer un schéma**, cliquez sur **Suivant**.

10. Dans la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**.

11. Sous la colonne **action** , développez **préparation du schéma**, recherchez le ** \<\> ** résultat de l’exécution réussie à la fin de chaque tâche pour vérifier que la préparation du schéma s’est correctement déroulée, fermez le journal, puis cliquez sur **Terminer**.

12. Attendez la fin de la réplication d’Active Directory ou forcez-la.

13. Vérifiez manuellement que les modifications de schéma ont été répliquées sur tous les autres contrôleurs de domaine. Pour plus d’informations, consultez [la rubrique vérification de la réplication de schéma Active Directory dans Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a>Pour utiliser des applets de commande afin de préparer le schéma de la forêt actuelle

1.  Ouvrez une session sur un ordinateur de la forêt en tant que membre du groupe Administrateurs du schéma et avec les droits d’administration sur le contrôleur de schéma.

2.  Installez les composants principaux de Lync Server comme suit :
    
    1.  À partir du dossier ou du support d’installation de Lync Server 2013, exécutez Setup. exe pour démarrer l’Assistant Déploiement de Lync Server.
    
    2.  Si le système vous invite à installer le package redistribuable Microsoft Visual C++, cliquez sur **Oui**.
    
    3.  La boîte de dialogue Configuration de Lync Server 2013 vous invite à indiquer un emplacement d’installation des fichiers Lync Server. Choisissez l’emplacement par défaut ou cliquez sur **Parcourir** pour accéder à un emplacement de votre choix, puis cliquez sur **Installer**.
    
    4.  Dans la page Contrat de licence, activez la case à cocher **J’accepte les termes du contrat de licence**, puis cliquez sur **OK**. Le programme d’installation installe les composants principaux de Lync Server 2013.

3.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

4.  Générer
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    Si vous ne spécifiez pas le paramètre LDF, la valeur par défaut est le chemin d’installation de Lync Server 2013 qui est lu à partir du Registre.
    
    Par exemple :
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  Utilisez l’applet de commande suivante pour vérifier si la préparation de schéma a été exécutée avec succès.
    
        Get-CsAdServerSchema 
    
    Cette applet de commande renvoie une valeur de l' **état\_\_\_actuel** de la version du schéma si la préparation du schéma a réussi.

6.  Attendez la fin de la réplication d’Active Directory ou forcez-la.

7.  Vérifiez manuellement que les modifications de schéma ont été répliquées sur tous les autres contrôleurs de domaine. Pour plus d’informations, consultez [la rubrique vérification de la réplication de schéma Active Directory dans Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Vérification de la réplication de schéma Active Directory dans Lync Server 2013](lync-server-2013-verifying-schema-replication.md)  


[Préparation du schéma Active Directory dans Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

