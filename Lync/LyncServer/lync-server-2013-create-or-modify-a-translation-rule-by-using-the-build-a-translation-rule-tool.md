---
title: Création ou modification d’une règle de conversion à l’aide de l’outil créer une règle de traduction
description: Créez ou modifiez une règle de conversion à l’aide de l’outil créer une règle de traduction.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule by using the Build a Translation Rule tool
ms:assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412909(v=OCS.15)
ms:contentKeyID: 48185224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 116048fff834e797bca76a895f45cd0ebc83ab94
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574520"
---
# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a>Création ou modification d’une règle de conversion à l’aide de l’outil créer une règle de traduction dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-05_

Procédez comme suit si vous souhaitez définir une règle de traduction en entrant un ensemble de valeurs dans l’outil **créer une règle de traduction** et en activant le panneau de configuration Lync Server pour générer le modèle de correspondance et la règle de traduction correspondants pour vous. Vous pouvez également écrire manuellement une expression régulière pour définir le modèle correspondant et la règle de traduction. Pour plus d’informations, reportez-vous à [créer ou modifier une règle de traduction manuellement dans Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>Pour définir une règle à l’aide de l’outil Créer une règle de traduction

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Pour commencer à définir une règle de traduction, suivez la procédure décrite dans [Configure a trunk with Media Bypass in Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) jusqu’à l’étape 10 ou [Configure a trunk without Media Bypass in Lync Server 2013 à l'](lync-server-2013-configure-a-trunk-without-media-bypass.md) étape 9.

4.  Sous **Nom** dans la page **Nouvelle règle de traduction** ou **Modifier la règle de traduction**, tapez un nom décrivant le modèle de numéro en cours de traduction.

5.  (Facultatif) Sous **Description**, entrez la description de la règle de traduction ; par exemple, **Appel longue distance international**.

6.  Dans la section **Créer une règle de traduction** de la boîte de dialogue, entrez des valeurs dans les champs suivants :
    
      - **Chiffres de début** : (Facultatif) Précisez les premiers chiffres des numéros que vous souhaitez faire correspondre avec le modèle. Par exemple, entrez **+** dans ce champ pour faire correspondre les numéros au format E. 164 (commençant par +).
    
      - **Longueur** : précisez le nombre de chiffres dans le modèle correspondant et choisissez si vous souhaitez que le modèle corresponde exactement à des numéros de cette longueur, à cette longueur au minimum et ou à une longueur quelconque. Par exemple, entrez **11** et sélectionnez l’option **Au moins** dans la liste déroulante pour faire correspondre les numéros dont la longueur est d’au minimum 11 chiffres.
    
      - **Chiffres à supprimer** : (Facultatif) Précisez le nombre de chiffres de début à supprimer. Par exemple, entrez **1** pour supprimer la **+** à partir du début du numéro.
    
      - **Chiffres à ajouter** : (Facultatif) Précisez les chiffres à ajouter aux numéros traduits. Par exemple, entrez **011** si vous souhaitez ajouter 011 aux numéros traduits au moment d’appliquer la règle.
    
    Les valeurs saisies dans ces champs sont reproduites dans les champs **Modèle à suivre** et **Règle de traduction**. Par exemple, si vous appliquez les valeurs de l’exemple précédent, l’expression régulière obtenue dans le champ **Modèle à suivre** est :
    
    **^\\+ ( \\ d {9} \\ +) $**
    
    Le champ **Règle de traduction** spécifie un modèle pour le format des numéros traduits. Ce modèle comprend deux parties :
    
      - Une valeur (par exemple, **$1**) qui représente le nombre de chiffres dans le modèle correspondant.
    
      - (Facultatif) Une valeur que vous pouvez ajouter par simple saisie dans le champ **Chiffres à ajouter**.
    
    Si vous utilisez les valeurs de l’exemple précédent, **011$1** apparaît dans le champ **Règle de traduction**.
    
    Lorsque cette règle de traduction est appliquée, +441235551010 devient 011441235551010.

7.  Cliquez sur **OK** pour enregistrer la règle de traduction.

8.  Cliquez sur **OK** pour enregistrer la configuration de la jonction.

9.  Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**.
    
    <div>
    

    > [!NOTE]
    > Chaque fois que vous créez ou modifiez une règle de traduction, vous devez exécuter la commande <STRONG>Valider tout</STRONG> pour publier la modification de la configuration. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publier des modifications en attente dans la configuration du routage des communications vocales dans Lync Server 2013</A> dans la documentation des opérations.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création ou modification manuelle d’une règle de traduction dans Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
[Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configuration d’une jonction sans déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[Publier les modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Options globales de déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

