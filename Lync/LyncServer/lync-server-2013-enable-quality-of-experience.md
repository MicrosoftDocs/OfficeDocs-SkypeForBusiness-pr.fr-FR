---
title: 'Lync Server 2013 : activer la qualité de l’interface'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Quality of Experience
ms:assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182583(v=OCS.15)
ms:contentKeyID: 48185385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dbccfd145ad8143edab10f92a10901e626075e2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735997"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-quality-of-experience-in-lync-server-2013"></a>Activer la qualité de l’interface dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

La qualité de l’expérience (QoE) enregistre des données numériques qui indiquent la qualité du média, ainsi que les informations sur les participants, les noms des appareils, les pilotes, les adresses IP et les types de point de terminaison impliqués dans les appels et les sessions. Pour plus d’informations, reportez-vous à la rubrique [planification de l’analyse dans Lync Server 2013](lync-server-2013-planning-for-monitoring.md) dans la documentation de planification.

Procédez comme suit pour activer la QoE dans toute l’entreprise ou dans chacun de ses sites.

<div>


> [!NOTE]  
> Pour activer la qualité de l’expérience, vous devez commencer par configurer la surveillance et une base de données principale de surveillance. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-deploying-monitoring.md">déploiement de la surveillance dans Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-qoe-by-using-lync-server-control-panel"></a>Pour activer QoE à l’aide du panneau de configuration de Lync Server

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Données de qualité de l’expérience**.

4.  Dans la page **Données de qualité de l’expérience**, cliquez sur la collection appropriée dans le tableau, sur **Action**, puis sur **Activer QoE**.

</div>

<div>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>Activation de QoE à l’aide d’applets de cmdlet Windows PowerShell

Vous pouvez activer le QoE en utilisant Windows PowerShell et l’applet **de cmdlet Set-CsQoEConfiguration** . Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».

<div>

## <a name="to-enable-qoe-for-a-single-location"></a>Pour activer la qualité de l’expérience pour un emplacement

  - Pour activer la qualité de l’expérience, définissez le paramètre EnableQoE sur True ($True).
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

</div>

<div>

## <a name="to-disable-qoe-for-a-single-location"></a>Pour désactiver la qualité de l’expérience pour un emplacement

  - Pour désactiver la qualité de l’expérience, définissez le paramètre EnableQoE sur False ($False). Ceci ne désinstalle pas la surveillance, mais suspend la collecte et le stockage des données de qualité de l’expérience.
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>Pour utiliser une commande pour activer la qualité de l’expérience dans plusieurs emplacements

  - Cette commande active la qualité de l’expérience pour tous les paramètres de configuration QoE actuellement utilisés dans votre organisation.
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True

</div>

Pour plus d’informations, consultez la rubrique [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Planification de la surveillance dans Lync Server 2013](lync-server-2013-planning-for-monitoring.md)  
[Déploiement de la surveillance dans Lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

