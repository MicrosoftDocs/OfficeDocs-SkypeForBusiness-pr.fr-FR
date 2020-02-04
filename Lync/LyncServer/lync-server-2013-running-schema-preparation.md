---
title: 'Lync Server 2013 : Exécution de la préparation du schéma'
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
ms.openlocfilehash: 06b02981e9baa589801839c8fd8c871ae35b0dde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a>Exécution de la préparation du schéma Active Directory dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-29_

Vous pouvez utiliser le programme d’installation ou les applets de contrôle Lync Server Management Shell pour préparer le schéma Active Directory. L’applet de contrôle qui étend le schéma Active Directory est **install-CsAdServerSchema**.

<div>


> [!NOTE]  
> L’applet de commande de préparation du schéma (<STRONG>install-CsAdServerSchema</STRONG>) doit accéder au maître de schéma, qui nécessite que le service Registre distant soit en cours d’exécution et que la clé de Registre à distance soit activée. Si le service Registre distant ne peut pas être activé sur le maître de schéma, vous pouvez exécuter l’applet de commande localement sur le maître de schéma. Pour plus d’informations sur l’accès à distance du Registre, voir l’article de la base de connaissances Microsoft 314837, « comment gérer <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>l’accès distant au registre ».



</div>

Après avoir terminé la préparation du schéma, vérifiez manuellement que la partition de schéma a été répliquée avant de procéder à la préparation de la forêt. Pour plus d’informations, consultez [vérification de la réplication de schéma Active Directory dans Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a>Pour utiliser le programme d’installation pour préparer le schéma de la forêt actuelle

1.  Ouvrez une session sur un serveur de votre forêt en tant que membre du groupe administrateurs de schéma et avec des droits d’administrateur sur le maître de schéma.

2.  À partir du dossier d’installation ou du média de Lync Server 2013, exécutez Setup. exe pour démarrer l’Assistant déploiement.

3.  Si vous êtes invité à installer le package redistribuable Microsoft Visual C++, cliquez sur **Oui**.

4.  La boîte de dialogue de configuration de Lync Server 2013 vous invite à entrer un emplacement d’installation des fichiers du serveur Lync. Choisissez l’emplacement par défaut ou **Naviguez** jusqu’à l’emplacement de votre choix, puis cliquez sur **installer**.

5.  Sur la page contrat de licence, activez la case à cocher **J’accepte les termes du contrat de licence**, puis cliquez sur **OK**.

6.  Le programme d’installation installe les composants principaux de Lync Server.

7.  Lorsque l’Assistant déploiement est prêt, cliquez sur **Préparer Active Directory**et attendez que l’état du déploiement soit déterminé.

8.  À l' **étape 1 : préparer le schéma**, cliquez sur **exécuter**.

9.  Sur la page **préparer le schéma** , cliquez sur **suivant**.

10. Dans la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**.

11. Sous la colonne **action** , développez **préparation du schéma**, recherchez le ** \<\> ** résultat de réussite d’exécution à la fin de chaque tâche pour vérifier que la préparation du schéma s’est déroulée correctement, fermez le journal, puis cliquez sur **Terminer**.

12. Attendez la fin de la réplication Active Directory pour qu’elle soit terminée ou forcée.

13. Assurez-vous manuellement que les modifications du schéma sont répliquées sur tous les autres contrôleurs de domaine. Pour plus d’informations, consultez [vérification de la réplication de schéma Active Directory dans Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a>Pour utiliser des applets de cmdlet pour préparer le schéma de la forêt actuelle

1.  Ouvrez une session sur un ordinateur de la forêt en tant que membre du groupe administrateurs de schéma et avec des droits d’administrateur sur le maître de schéma.

2.  Installez les composants principaux de Lync Server comme suit :
    
    1.  À partir du dossier d’installation ou du média de Lync Server 2013, exécutez Setup. exe pour démarrer l’Assistant Déploiement de Lync Server.
    
    2.  Si vous êtes invité à installer le package redistribuable Microsoft Visual C++, cliquez sur **Oui**.
    
    3.  La boîte de dialogue de configuration de Lync Server 2013 vous invite à entrer un emplacement d’installation des fichiers du serveur Lync. Choisissez l’emplacement par défaut ou **Naviguez** jusqu’à l’emplacement de votre choix, puis cliquez sur **installer**.
    
    4.  Sur la page contrat de licence, activez la case à cocher **J’accepte les termes du contrat de licence**, puis cliquez sur **OK**. Le programme d’installation installe les composants principaux de Lync Server 2013.

3.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

4.  Exécutez :
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    Si vous ne spécifiez pas le paramètre LDF, la valeur par défaut correspond au chemin d’accès de l’installation de Lync Server 2013 lu à partir du Registre.
    
    Par exemple :
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  Utilisez l’applet de commande suivante pour vérifier que la préparation du schéma s’est terminée.
    
        Get-CsAdServerSchema 
    
    Cette applet de contrôle renvoie une valeur de l' **état\_\_\_de version du schéma en cours** si la préparation du schéma a réussi.

6.  Attendez la fin de la réplication Active Directory pour qu’elle soit terminée ou forcée.

7.  Assurez-vous manuellement que les modifications du schéma sont répliquées sur tous les autres contrôleurs de domaine. Pour plus d’informations, consultez [vérification de la réplication de schéma Active Directory dans Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

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

