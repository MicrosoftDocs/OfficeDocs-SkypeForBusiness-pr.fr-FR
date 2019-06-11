---
title: 'Lync Server 2013: déploiement de l’outil SEFAUtil'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy the SEFAUtil tool
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945659(v=OCS.15)
ms:contentKeyID: 51541534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0783ab251359582d232d558da2161a149dea5117
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a>Deploy the SEFAUtil tool in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-01-30_

Pour déployer et gérer la cueillette des appels de groupe, vous devez utiliser l’outil Kit de ressources SEFAUtil. L’outil fait partie des outils du kit de ressources Lync Server 2013. Pour pouvoir installer SEFAUtil, vous devez disposer d’un pool d’applications approuvé dans votre topologie, spécifier SEFAUtil en tant qu’application approuvée et activer la topologie.

<div>


> [!IMPORTANT]  
> Le Kit de développement logiciel (SDK) Microsoft Unified Communications Managed API (UCMA) 3.0 Core doit être sur les ordinateurs sur lesquels vous voulez exécuter l’outil SEFAUtil.



</div>

Vous pouvez exécuter SEFAUtil dans n’importe quel pool frontal de votre déploiement.

<div>


> [!NOTE]  
> Pour plus d’informations sur l’exécution de SEFAUtil, voir l’article de blog TechNet intitulé «Comment puis-je lancer SEFAutil?» à <A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>.



</div>

<div>

## <a name="to-deploy-sefautil"></a>Pour déployer SEFAUtil

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans la rubrique [autorisations de configuration du délégué dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  L’outil SEFAUtil ne peut être exécuté que sur un ordinateur qui fait partie d’un pool d’applications approuvées. Le cas échéant, définissez un pool d’applications approuvé pour le pool frontal sur lequel vous envisagez d’exécuter SEFAUtil. Dans la ligne de commande, exécutez la commande suivante :
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  Définissez l’outil SEFAUtil en tant qu’application approuvée. Sur la ligne de commande, exécutez :
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez utiliser un autre port si nécessaire.

    
    </div>

5.  Activez la topologie avec vos modifications. Sur la ligne de commande, exécutez :
    
        Enable-CsTopology

6.  Installez les outils du kit de ressources de Lync Server 2013 sur un serveur frontal qui se trouve dans le pool d’applications approuvé que vous avez créé à l’étape 3.

7.  Vérifiez que l’outil SEFAUtil s’exécute correctement ainsi :
    
    1.  Exécutez l’outil à partir de l’invite de commande Windows avec des droits d’administrateur pour afficher les paramètres de transfert d’appel d’un utilisateur de votre déploiement.
        
        <div>
        

        > [!NOTE]  
        > L’outil se trouve à l’emplacement \Program Files\Microsoft Lync Server 2013 \ reskit.

        
        </div>
    
    2.  Affichez les paramètres de transfert d’appel d’un utilisateur. Sur la ligne de commande, exécutez :
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        Les paramètres de transfert d’appel de l’utilisateur s’afficheront.

</div>

</div>

<span> </span>

</div>

</div>

</div>

