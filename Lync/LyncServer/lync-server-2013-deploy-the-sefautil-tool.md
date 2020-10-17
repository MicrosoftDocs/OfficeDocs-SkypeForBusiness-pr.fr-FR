---
title: 'Lync Server 2013 : déploiement de l’outil SEFAUtil'
description: 'Lync Server 2013 : déployez l’outil SEFAUtil.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy the SEFAUtil tool
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945659(v=OCS.15)
ms:contentKeyID: 51541534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 311f14f33dff30b388836a7f02483c4afe5da1b1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558610"
---
# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a>Déployer l’outil SEFAUtil dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-01-30_

Pour déployer et gérer la prise d’appel de groupe, vous devez utiliser l’outil Kit de ressources de SEFAUtil. L’outil fait partie des outils du kit de ressources Lync Server 2013. Avant de pouvoir installer SEFAUtil, vous devez disposer d’un pool d’applications approuvées dans votre topologie, spécifier SEFAUtil comme application approuvée et activer la topologie.

<div>


> [!IMPORTANT]  
> Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK doit être installé sur tout ordinateur sur lequel vous envisagez d’exécuter l’outil SEFAUtil.



</div>

Vous pouvez exécuter l’SEFAUtil dans n’importe quel pool frontal de votre déploiement.

<div>


> [!NOTE]  
> Pour plus d’informations sur l’exécution d’SEFAUtil, consultez l’article du blog TechNet « How to get SEFAutil Running ? » à l’adresse <A href="https://go.microsoft.com/fwlink/?linkid=278940">https://go.microsoft.com/fwlink/?LinkId=278940</A> .



</div>

<div>

## <a name="to-deploy-sefautil"></a>Pour déployer SEFAUtil

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  L’outil SEFAUtil peut être exécuté uniquement sur un ordinateur qui fait partie d’un pool d’applications approuvées. Si nécessaire, définissez un pool d’applications approuvées pour le pool frontal dans lequel vous prévoyez d’exécuter SEFAUtil. À partir de la ligne de commande, exécutez la commande suivante :
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  Définissez l’outil SEFAUtil en tant qu’application approuvée. À partir de la ligne de commande, exécutez la commande suivante :
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez utiliser un autre port si nécessaire.

    
    </div>

5.  Activez la topologie avec vos modifications. À partir de la ligne de commande, exécutez la commande suivante :
    
        Enable-CsTopology

6.  Installez les outils du kit de ressources Lync Server 2013 sur un serveur frontal qui se trouve dans le pool d’applications approuvées que vous avez créé à l’étape 3.

7.  Vérifiez que l’outil SEFAUtil s’exécute correctement, comme suit :
    
    1.  Exécutez l’outil à partir de l’invite de commandes Windows avec les privilèges d’administrateur pour afficher les paramètres de transfert d’appel d’un utilisateur dans votre déploiement.
        
        <div>
        

        > [!NOTE]  
        > L’outil se trouve à l’emplacement \Program Files\Microsoft Lync Server 2013 \ reskit.

        
        </div>
    
    2.  Afficher les paramètres de transfert d’appel d’un utilisateur. À partir de la ligne de commande, exécutez la commande suivante :
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        Les paramètres de transfert d’appel de l’utilisateur seront affichés.

</div>

</div>

<span> </span>

</div>

</div>

</div>

