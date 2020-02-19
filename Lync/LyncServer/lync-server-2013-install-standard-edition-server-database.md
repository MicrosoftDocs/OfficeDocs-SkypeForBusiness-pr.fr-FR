---
title: 'Lync Server 2013 : installation de la base de données serveur Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0386caebab3b50854ae608d947b6cd674922c155
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a>Installer la base de données de serveur Standard Edition pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

La configuration d’un serveur Standard Edition Server en tant que seul serveur dans votre infrastructure qui héberge des utilisateurs diffère de celle des autres serveurs dans la mesure où il existe une sélection dans l' **Assistant Déploiement** spécifiquement pour la configuration du serveur initial.

<div>

## <a name="to-install-a-standard-edition-server"></a>Pour installer un serveur Standard Edition

1.  Ouvrez une session sur le serveur sur lequel vous allez installer le serveur Standard Edition en tant qu’administrateur local ou en tant que domaine équivalent.

2.  Si vous n’avez pas préparé les services de domaine Active Directory, effectuez d’abord ces procédures. Pour plus d’informations, consultez la rubrique [préparation des services de domaine Active Directory pour Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

3.  Dans l’Assistant Déploiement Lync Server, cliquez sur **préparer d’abord le serveur Standard Edition**.

4.  Dans la page **Préparer le serveur Standard Edition**, cliquez sur **Suivant**.

5.  Sur la page **exécution de commandes** , SQL Server 2012 Express est installé en tant que magasin central de gestion. Les règles de pare-feu nécessaires sont créées. Lorsque l’installation de la base de données et des logiciels prérequis est terminée, cliquez sur **Terminer**.
    
    <div>
    

    > [!NOTE]  
    > L’installation initiale peut durer un certain temps sans que les mises à jour ne soient visibles sur l’écran récapitulatif des résultats de la commande. Ceci est dû à l’installation de SQL Server Express. Pour surveiller l’installation de la base de données, utilisez le Gestionnaire des tâches.

    
    </div>

6.  Sur la page Assistant Déploiement Lync Server, cliquez sur **installer le générateur de topologie** si vous n’avez pas préalablement installé les outils d’administration. Pour plus d’informations, reportez-vous à la rubrique [install Lync Server 2013 administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).

7.  Vérifiez que des coches vertes apparaissent bien en regard de « Préparer Active Directory », « Préparer le serveur Standard Edition » et « Installer le Générateur de topologie ».

</div>

</div>

<span> </span>

</div>

</div>

</div>

