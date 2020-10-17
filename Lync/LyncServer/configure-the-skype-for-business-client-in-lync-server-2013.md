---
title: Configurer le client Skype entreprise dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20980f0f0b6697eada6c237aa8d2297b0fd227d9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503301"
---
# <a name="configure-the-client-experience-with-skype-for-business"></a>Configuration de l’expérience client avec Skype entreprise

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-09-17_

**Résumé :** Cette rubrique décrit comment configurer l’expérience client pour les utilisateurs de clients Skype entreprise dans un environnement Lync Server 2013. Vous pouvez configurer l’expérience client uniquement si vous exécutez Lync Server 2013 avec la mise à jour cumulative de décembre 2014 (5.0.8308.857) ou une version ultérieure. Pour plus d’informations sur la mise à jour de Lync Server 2013, voir [mises à jour pour Lync server 2013](https://go.microsoft.com/fwlink/p/?linkid=532651).

Skype entreprise offre une nouvelle expérience utilisateur basée sur l’expérience de produit client Skype. En plus de toutes les fonctionnalités de Lync, Skype entreprise offre de nouvelles fonctionnalités avec des contrôles simplifiés et des icônes familières. Pour plus d’informations sur la nouvelle expérience client, voir [Lync est maintenant Skype entreprise--voir what’s New](https://go.microsoft.com/fwlink/?linkid=529022).

Lync Server 2013 prend en charge la nouvelle expérience client Skype entreprise, ainsi que l’expérience client Lync. En tant qu’administrateur, vous pouvez choisir l’expérience client préférée pour vos utilisateurs. Par exemple, vous pouvez déployer l’expérience client Lync jusqu’à ce que les utilisateurs de votre organisation soient entièrement formés à la nouvelle expérience Skype entreprise. Si vous n’avez pas encore mis à niveau tous les utilisateurs vers Skype entreprise Server 2015, vous souhaiterez peut-être que tous les utilisateurs bénéficient de la même expérience client jusqu’à ce que tous soient mis à niveau vers le nouveau serveur.

<div>


> [!IMPORTANT]  
> Si votre organisation a à la fois Skype entreprise Server 2015 et Lync Server 2013 déployés, l’expérience client par défaut varie en fonction des versions du serveur et des paramètres de l’interface utilisateur. Lorsque les utilisateurs lancent Skype entreprise pour la première fois, ils voient toujours l’interface utilisateur de Skype entreprise, même si vous avez sélectionné l’interface utilisateur Lync. Après quelques minutes, les utilisateurs sont invités à passer en mode Lync. Pour plus d’informations, voir <STRONG>First Launch client Behavior</STRONG> plus loin dans cette rubrique.



</div>

<div>


> [!NOTE]  
> L’expérience client Lync 2013 n’est pas une option pour les versions clientes de Skype entreprise 2016. Avant de configurer votre environnement client pour qu’il utilise le client Lync 2013, vérifiez la version du client pour vous assurer qu’elle ne commence pas par le numéro 16 ; par exemple : 16. x.x.x.



</div>

<div>

## <a name="configure-the-client-experience"></a>Configurer l’expérience client

Vous pouvez spécifier l’expérience client que les utilisateurs de votre organisation verront à l’aide de la cmdlet **Set-CSClientPolicy** avec le paramètre EnableSkypeUI. La commande suivante sélectionne l’expérience client Skype entreprise pour tous les utilisateurs de votre organisation concernés par la stratégie globale (Rappelez-vous que les stratégies de site ou spécifiques à l’utilisateur remplacent la stratégie globale) :

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

La commande suivante sélectionne l’expérience client Lync pour tous les utilisateurs de votre organisation concernés par la stratégie globale :

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

La commande suivante sélectionne l’expérience client Skype entreprise pour tous les utilisateurs au sein du site de Redmond :

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

Si vous souhaitez configurer l’expérience client pour des utilisateurs spécifiques au sein de votre organisation, vous pouvez créer une nouvelle stratégie utilisateur à l’aide de la cmdlet **New-CsClientPolicy** , puis affecter la stratégie à des utilisateurs spécifiques à l’aide de la cmdlet **Grant-CsClientPolicy** .

Par exemple, la commande suivante crée une nouvelle stratégie client, SalesClientUI, qui sélectionne l’expérience client Skype entreprise :

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

La commande suivante affecte la stratégie, SalesClientUI, à tous les membres du service des ventes :

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a>Comportements de client de premier lancement

Par défaut, lorsque les utilisateurs lancent Skype entreprise pour la première fois, ils voient toujours l’interface utilisateur de Skype entreprise, même si vous avez sélectionné l’expérience client Lync en définissant la valeur du paramètre EnableSkypeUI sur $False comme décrit précédemment. Après quelques minutes, les utilisateurs sont invités à passer en mode Lync.

Si vous souhaitez afficher l’interface utilisateur Lync lorsque les utilisateurs lancent le client Skype entreprise pour la première fois, suivez ces étapes avant le démarrage du client pour la première fois après sa mise à jour :

1.  Vérifiez que la valeur de `EnableSkypeUI` est définie sur $false dans la stratégie que vous utilisez comme décrit précédemment.

2.  Mettez à jour le registre système sur l’ordinateur de l’utilisateur. Vous devez effectuer cette opération avant la première exécution du client Skype entreprise, et vous ne devez effectuer cette opération qu’une seule fois. Pour plus d’informations sur la création d’un objet de stratégie de groupe pour mettre à jour le registre sur un ordinateur joint à un domaine, voir la section plus loin dans cette rubrique.
    
    Dans la clé ** \[ HKEY \_ Current \_ User \\ Software \\ Microsoft \\ Office \\ \] Lync** , créez une valeur **binaire** .
    
    Le **nom** de la valeur doit être **EnableSkypeUI**et les **données de valeur** doivent être définies sur **00 00 00 00**.
    
    La clé doit ressembler à ce qui suit :
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

L’interface utilisateur de Lync apparaît maintenant lorsque les utilisateurs lancent le client Skype entreprise pour la première fois.

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Contrôler l’affichage du didacticiel de l’écran d’accueil

Lorsque les utilisateurs ouvrent le client Skype entreprise, le comportement par défaut consiste à afficher un écran d’accueil qui inclut *7 conseils rapides que la plupart des personnes demandent*. Vous pouvez désactiver l’affichage de l’écran d’accueil tout en autorisant les utilisateurs à accéder au didacticiel en ajoutant la valeur de Registre suivante sur l’ordinateur client :

Dans la clé ** \[ \_ \_ \\ \\ Microsoft \\ Office \\ 15,0 \\ Lync \] Software User Software** , créez une nouvelle **valeur DWORD (32 bits)**. Le **nom** de la valeur doit être **IsBasicTutorialSeenByUser**et les **données de valeur** doivent être définies sur **1**.

La clé doit ressembler à ce qui suit :

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a>Désactivation du didacticiel client

Si vous ne souhaitez pas que vos utilisateurs puissent accéder au didacticiel, vous pouvez désactiver le didacticiel client avec la valeur de Registre suivante :

Dans la clé ** \[ \_ \_ \\ \\ Microsoft \\ Office \\ 15,0 \\ Lync \] Software User Software** , créez une nouvelle **valeur DWORD (32 bits)**. Le **nom** de la valeur doit être **TutorialFeatureEnabled**et les **données de valeur** doivent être définies sur **0**.

    "TutorialFeatureEnabled"=dword:00000000

Vous pouvez réactiver le didacticiel en définissant la **valeur** sur **1**.

</div>

</div>

<div>

## <a name="default-client-experiences"></a>Expériences client par défaut

Si votre organisation a à la fois Skype entreprise Server 2015 et Lync Server déployés, l’expérience client varie en fonction des versions de serveur et du paramètre de l’interface utilisateur Skype. Le tableau suivant indique l’expérience client initiale en fonction de la version du serveur et du paramètre de l’interface utilisateur :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Version du serveur</p></th>
<th><p>Paramètre EnableSkypeUI</p></th>
<th><p>Expérience client</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype Entreprise Server 2015</p></td>
<td><p>Par défaut</p></td>
<td><p>Skype Entreprise</p></td>
</tr>
<tr class="even">
<td><p>Skype Entreprise Server 2015</p></td>
<td><p>Vrai</p></td>
<td><p>Skype Entreprise</p></td>
</tr>
<tr class="odd">
<td><p>Skype Entreprise Server 2015</p></td>
<td><p>False</p></td>
<td><p>L’utilisateur a demandé à passer en mode Lync (l’utilisateur peut passer à Skype entreprise ultérieurement si vous modifiez le paramètre de l’interface utilisateur pour $true)</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 ou Lync Server 2013 (avec les correctifs appropriés)</p></td>
<td><p>Par défaut</p></td>
<td><p>L’utilisateur a demandé à passer en mode Lync (l’utilisateur peut passer à Skype entreprise ultérieurement si vous modifiez le paramètre de l’interface utilisateur pour $true)</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 ou Lync Server 2013 (avec les correctifs appropriés)</p></td>
<td><p>Vrai</p></td>
<td><p>Skype Entreprise</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 ou Lync Server 2013 (avec les correctifs appropriés)</p></td>
<td><p>False</p></td>
<td><p>L’utilisateur a demandé à passer en mode Lync (l’utilisateur peut passer à Skype entreprise ultérieurement si vous modifiez le paramètre de l’interface utilisateur pour $true)</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 ou Lync Server 2013 (sans correctifs)</p></td>
<td><p>Par défaut</p></td>
<td><p>L’utilisateur a demandé à passer à l’expérience client Lync (l’utilisateur ne peut pas passer à Skype entreprise plus tard)</p></td>
</tr>
</tbody>
</table>


Le tableau suivant indique l’expérience client lorsque l’administrateur modifie le paramètre initial de l’expérience utilisateur Skype :


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Version du serveur</p></th>
<th><p>Paramètre de l’interface utilisateur Skype</p></th>
<th><p>Interface utilisateur du client = Lync</p></th>
<th><p>Interface utilisateur du client = Skype entreprise</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype Entreprise Server 2015</p></td>
<td><p>Vrai</p></td>
<td><p>Utilisateur invité à passer à Skype entreprise</p></td>
<td><p>Skype Entreprise</p></td>
</tr>
<tr class="even">
<td><p>Skype Entreprise Server 2015</p></td>
<td><p>False</p></td>
<td><p>Interface utilisateur Lync</p></td>
<td><p>Utilisateur invité à basculer vers l’interface utilisateur Lync</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 ou Lync Server 2013 (avec les correctifs appropriés)</p></td>
<td><p>Vrai</p></td>
<td><p>Utilisateur invité à passer à Skype entreprise</p></td>
<td><p>Skype Entreprise</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 ou Lync Server 2013 (avec les correctifs appropriés)</p></td>
<td><p>False</p></td>
<td><p>Interface utilisateur Lync</p></td>
<td><p>Utilisateur invité à basculer vers l’interface utilisateur Lync</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 ou Lync Server 2013 (sans correctifs)</p></td>
<td><p>Par défaut</p></td>
<td><p>Mode Lync (impossible de basculer vers Skype entreprise)</p></td>
<td><p>Interface utilisateur Lync (impossible de basculer vers Skype entreprise)</p></td>
</tr>
</tbody>
</table>


Les versions des correctifs nécessaires à la gestion de la configuration du client Skype entreprise sont les suivantes :

  - Lync Server 2010-mise à jour cumulative de février 2015 (4.0.7577.710) pour Lync Server 2010. Pour plus d’informations, consultez la rubrique [mises à jour pour Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkid=532771)

  - Lync Server 2013-mise à jour cumulative 2014 de décembre (5.0.8308.857) pour Lync Server 2013. Pour plus d’informations, consultez la rubrique [mises à jour pour Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532772).

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Créer un objet de stratégie de groupe pour modifier le registre sur un ordinateur joint à un domaine

La mise à jour du Registre pour afficher l’expérience client Lync la première fois qu’un utilisateur lance le client Skype entreprise, ne doit être exécutée qu’une seule fois. Si vous utilisez un objet de stratégie de groupe (GPO) pour mettre à jour le registre, vous devez définir l’objet pour créer une nouvelle valeur au lieu de mettre à jour les données de la valeur. Lorsque l’objet de stratégie de groupe est appliqué, si la nouvelle valeur n’existe pas, l’objet de stratégie de groupe le crée et définit la valeur sur 0.

La procédure suivante décrit comment modifier le registre afin que l’expérience client Lync soit affichée la première fois qu’un utilisateur lance Skype entreprise. Vous pouvez également utiliser cette procédure pour mettre à jour le registre afin de désactiver le didacticiel de l’écran d’accueil, comme décrit précédemment.

**Pour créer l’objet GPO**

1.  Démarrez la **console de gestion des stratégies de groupe**.
    
    Pour plus d’informations sur l’utilisation de la console de gestion des stratégies de groupe, voir [console de gestion des stratégies de groupe](https://go.microsoft.com/fwlink/?linkid=532759).

2.  Cliquez avec le bouton droit sur le nœud **objets de stratégie de groupe** et sélectionnez **nouveau** dans le menu.

3.  Dans la boîte de dialogue **nouvel objet GPO** , entrez un nom pour l’objet de stratégie de groupe, par exemple, **MakeLyncDefaultUI**, puis cliquez sur **OK**.

4.  Cliquez avec le bouton droit sur le nouvel objet GPO que vous venez de créer, puis sélectionnez **modifier** dans le menu.

5.  Dans l' **éditeur de gestion des stratégies de groupe**, développez **Configuration utilisateur**, **Préférences**, **Paramètres Windows**, puis sélectionnez le nœud **Registre** .

6.  Cliquez avec le bouton droit sur le nœud de **Registre** , puis sélectionnez **nouvel** \> **élément de Registre**.

7.  Dans la boîte de dialogue **nouvelles propriétés de Registre** , mettez à jour les éléments suivants :
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Champ</th>
    <th>Valeur à sélectionner ou entrer</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Action</strong></p></td>
    <td><p><strong>Create</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Ruche</strong></p></td>
    <td><p>HKEY_CURRENT_USER</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Chemin d’accès à la clé</strong></p></td>
    <td><p>Software\Microsoft\Office\Lync</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Nom de la valeur</strong></p></td>
    <td><p>EnableSkypeUI</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Type de valeur</strong></p></td>
    <td><p>REG_BINARY</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Données de la valeur</strong></p></td>
    <td><p>00000000</p></td>
    </tr>
    </tbody>
    </table>


8.  Cliquez sur **OK** pour enregistrer vos modifications, puis fermez l’objet GPO.

Ensuite, vous devez lier l’objet de stratégie de groupe que vous avez créé au groupe d’utilisateurs auquel vous souhaitez affecter la stratégie, tel qu’une unité d’organisation.

**Pour utiliser l’objet GPO pour affecter la stratégie**

1.  Dans la console de gestion des stratégies de groupe, cliquez avec le bouton droit sur l’unité d’organisation à laquelle vous souhaitez affecter la stratégie, puis sélectionnez **lier un objet de stratégie**de groupe existant.

2.  Dans la boîte de dialogue **Sélectionner un objet GPO** , sélectionnez l’objet de stratégie de groupe que vous avez créé, puis cliquez sur **OK**.

3.  Sur l’ordinateur de l’utilisateur cible, ouvrez une invite de commandes et tapez la commande suivante :
    
    **gpupdate/target : utilisateur**
    
    Message « mise à jour de la stratégie... » est affiché pendant l’application de l’objet de stratégie de groupe. Une fois l’opération terminée, le message « la mise à jour de la stratégie utilisateur s’est terminée correctement » s’affiche.

4.  Depuis l'invite de commandes, entrez la commande suivante :
    
    **gpresult/r**
    
    Vous devriez voir « objets de stratégie de groupe affectés » avec le nom de l’objet de stratégie de groupe que vous avez créé ci-dessous.

Vous pouvez également vérifier que l’objet de stratégie de groupe a correctement mis à jour le registre sur l’ordinateur d’un utilisateur en examinant le registre. Ouvrez l’éditeur du Registre et accédez à la clé ** \[ HKEY \_ Current \_ User \\ Software \\ Microsoft \\ Office \\ Lync \] ** . Si l’objet GPO a correctement mis à jour le registre, vous verrez une valeur nommée EnableSkypeUI avec une valeur de 0.

</div>

</div>

<span> </span>

</div>

</div>

</div>

