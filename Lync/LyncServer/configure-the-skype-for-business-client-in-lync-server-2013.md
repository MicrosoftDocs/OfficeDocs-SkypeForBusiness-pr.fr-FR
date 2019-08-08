---
title: Configurer le client Skype entreprise dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 632eed40992bfcff53072d618313afe3501431be
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-client-experience-with-skype-for-business"></a>Configuration de l’expérience client avec Skype Entreprise

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2015-09-17_

**Résumé:** Cette rubrique décrit comment configurer l’utilisation du client pour les utilisateurs de clients Skype entreprise dans un environnement Lync Server 2013. Vous pouvez configurer l’interface client uniquement si vous exécutez Lync Server 2013 avec la mise à jour cumulative 2014 de décembre (5.0.8308.857) ou une version ultérieure. Pour plus d’informations sur la mise à jour de Lync Server 2013, voir [mises à jour de Lync server 2013](http://go.microsoft.com/fwlink/p/?linkid=532651).

Skype entreprise fournit une nouvelle interface utilisateur qui repose sur l’utilisation des produits Skype. Outre l’ensemble des fonctionnalités de Lync, Skype entreprise fournit de nouvelles fonctionnalités avec des contrôles simplifiés et des icônes familières. Pour plus d’informations sur la nouvelle interface client, voir [Lync devient Skype entreprise--](http://go.microsoft.com/fwlink/?linkid=529022)nouveautés.

Lync Server 2013 prend en charge la nouvelle interface client Skype entreprise, ainsi que l’interface du client Lync. En tant qu’administrateur, vous pouvez choisir la meilleure expérience client pour vos utilisateurs. Par exemple, vous souhaiterez peut-être déployer l’interface du client Lync jusqu’à ce que les utilisateurs de votre organisation aient pleinement formé la nouvelle interface Skype entreprise. Ou bien, si vous n’avez pas encore effectué la mise à niveau de tous les utilisateurs vers Skype entreprise Server 2015, vous souhaiterez peut-être que tous les utilisateurs disposent de la même interface utilisateur jusqu’à ce qu’ils soient mis à niveau vers le nouveau serveur.

<div>


> [!IMPORTANT]  
> Si votre organisation utilise à la fois Skype entreprise Server Server 2015 et Lync Server 2013, l’interface client par défaut varie en fonction des versions de serveur et des paramètres d’interface utilisateur. Lorsque les utilisateurs lancent Skype entreprise pour la première fois, l’interface utilisateur de Skype entreprise est toujours affichée, même si vous avez sélectionné l’interface utilisateur de Lync. Après plusieurs minutes, l’utilisateur est invité à basculer vers le mode Lync. Pour plus d’informations, voir <STRONG>Comportements client au premier lancement</STRONG> dans la suite de cette rubrique.



</div>

<div>


> [!NOTE]  
> L’interface du client 2013 de Lync n’est pas disponible pour les versions clientes de Skype entreprise 2016. Avant de configurer votre environnement client pour qu’il utilise le client 2013 Lync, vérifiez la version du client pour vous assurer qu’il ne commence pas par le numéro 16; par exemple: 16. x.x.x.



</div>

<div>

## <a name="configure-the-client-experience"></a>Configure the client experience

Vous pouvez spécifier l’utilisation du client que les utilisateurs de votre organisation verront à l’aide de l’applet de passe **Set-CSClientPolicy** avec le paramètre EnableSkypeUI. La commande suivante sélectionne l’interface client Skype entreprise pour tous les utilisateurs de votre organisation concernés par la politique globale (n’oubliez pas que les stratégies de site ou d’utilisateur remplacent la stratégie globale):

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

La commande suivante sélectionne l’interface du client Lync pour tous les utilisateurs de votre organisation concernés par la stratégie globale:

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

La commande suivante sélectionne l’interface client Skype entreprise pour tous les utilisateurs du site de Redmond:

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

Si vous voulez configurer l’utilisation du client pour des utilisateurs spécifiques au sein de votre organisation, vous pouvez créer une nouvelle stratégie d’utilisateur à l’aide de l’applet **de nouvelle** applet de CsClientPolicy, puis affecter la stratégie à des utilisateurs spécifiques à l’aide de l’applet de passe **CsClientPolicy** applet.

Par exemple, la commande suivante crée une nouvelle stratégie client, SalesClientUI, qui sélectionne l’interface du client Skype entreprise:

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

La commande suivante affecte la stratégie, SalesClientUI, à tous les membres du service commercial :

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a>Comportements client au premier lancement

Par défaut, lorsque les utilisateurs lancent Skype entreprise pour la première fois, l’interface utilisateur de Skype entreprise est toujours affichée, même si vous avez sélectionné l’environnement du client Lync en définissant la valeur du paramètre EnableSkypeUI sur $False comme décrit précédemment . Après quelques minutes, les utilisateurs sont invités à passer en mode Lync.

Si vous souhaitez afficher l'interface utilisateur Lync lorsque les utilisateurs lancent le client Skype Entreprise pour la première fois, suivez cette procédure avant le premier démarrage du client après la mise à jour :

1.  Vérifiez que la valeur de `EnableSkypeUI` est définie sur $false dans la stratégie que vous utilisez, comme décrit précédemment.

2.  Mettez à jour le registre système sur l'ordinateur de l'utilisateur. Vous devez le faire avant que les utilisateurs lancent le client Skype Entreprise la première fois et vous ne devez effectuer cette opération qu'une seule fois. Pour plus d'informations sur la création d'un objet de stratégie de groupe pour mettre à jour le registre sur un ordinateur joint à un domaine, reportez-vous à la section dans la suite de cette rubrique.
    
    Dans la ** \[clé\_Microsoft\_\\Office\\\\Lync\\\] logiciel de l’utilisateur actuel** , créez une valeur **binaire** .
    
    Le **nom de la valeur** doit être **EnableSkypeUI** et les **données de la valeur** doivent être définies sur la valeur **00 00 00 00**.
    
    La clé doit se présenter comme celle-ci :
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

L'interface utilisateur de Lync s'affiche maintenant lorsque les utilisateurs lancent le client Skype Entreprise pour la première fois.

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Contrôler l’affichage du didacticiel de l’écran d’accueil

Lorsque les utilisateurs ouvrent le client Skype entreprise, le comportement par défaut consiste à afficher un écran d’accueil incluant *7 conseils rapides pour la plupart des personnes*. Vous pouvez désactiver l'affichage de l'écran d'accueil, mais permettre quand même aux utilisateurs d'accéder au didacticiel en ajoutant la valeur de registre ci-dessous sur l'ordinateur client :

Dans la ** \[clé\_Microsoft\_\\Office\\\\15,0\\\\du logiciel de l’utilisateur HKEY actuel, créez une nouvelle valeur DWORD (32 bits\] ** **)**. Le **nom de la valeur** doit être **IsBasicTutorialSeenByUser** et les **données de valeur** doivent être définies sur **1**.

La clé doit se présenter comme celle-ci :

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a>Désactivation du didacticiel client

Si vous ne voulez pas que vos utilisateurs puissent accéder au didacticiel, vous pouvez désactiver le didacticiel du client avec la valeur de registre suivante :

Dans la ** \[clé\_Microsoft\_\\Office\\\\15,0\\\\du logiciel de l’utilisateur HKEY actuel, créez une nouvelle valeur DWORD (32 bits\] ** **)**. Le **nom de la valeur** doit être **TutorialFeatureEnabled** et les **données de valeur** doivent être définies sur **0**.

    "TutorialFeatureEnabled"=dword:00000000

Vous pouvez réactiver le didacticiel en définissant les **données de valeur** sur **1**.

</div>

</div>

<div>

## <a name="default-client-experiences"></a>Expériences client par défaut

Si votre organisation utilise à la fois Skype entreprise Server Server 2015 et Lync Server, l’environnement client varie en fonction des versions de serveur et du paramètre d’interface utilisateur de Skype. Le tableau ci-dessous montre l’expérience client initiale en fonction de la version du serveur et du paramètre de l’interface utilisateur :


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
<td><p>Skype Entreprise</p></td>
</tr>
<tr class="even">
<td><p>Skype Entreprise Server 2015</p></td>
<td><p>True</p></td>
<td><p>Skype Entreprise</p></td>
</tr>
<tr class="odd">
<td><p>Skype Entreprise Server 2015</p></td>
<td><p>False</p></td>
<td><p>Utilisateur invité à basculer vers le mode Lync (l’utilisateur peut basculer vers Skype entreprise plus tard si vous modifiez le paramètre de l’interface utilisateur en $true)</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 ou Lync Server 2013 (avec les correctifs appropriés)</p></td>
<td><p>Par défaut</p></td>
<td><p>Utilisateur invité à basculer vers le mode Lync (l’utilisateur peut basculer vers Skype entreprise plus tard si vous modifiez le paramètre de l’interface utilisateur en $true)</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 ou Lync Server 2013 (avec les correctifs appropriés)</p></td>
<td><p>True</p></td>
<td><p>Skype Entreprise</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 ou Lync Server 2013 (avec les correctifs appropriés)</p></td>
<td><p>False</p></td>
<td><p>Utilisateur invité à basculer vers le mode Lync (l’utilisateur peut basculer vers Skype entreprise plus tard si vous modifiez le paramètre de l’interface utilisateur en $true)</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 ou Lync Server 2013 (sans correctifs)</p></td>
<td><p>Par défaut</p></td>
<td><p>Utilisateur invité à basculer vers l’utilisation du client Lync (l’utilisateur ne peut pas basculer vers Skype entreprise plus tard)</p></td>
</tr>
</tbody>
</table>


Le tableau suivant indique l’environnement client lorsque l’administrateur modifie le paramètre initial de l’interface utilisateur de Skype:


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
<th><p>Paramètre d’interface utilisateur de Skype</p></th>
<th><p>Interface utilisateur du client = Lync</p></th>
<th><p>UI client = Skype Entreprise</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype Entreprise Server 2015</p></td>
<td><p>True</p></td>
<td><p>Utilisateur invité à basculer sur Skype entreprise</p></td>
<td><p>Skype Entreprise</p></td>
</tr>
<tr class="even">
<td><p>Skype Entreprise Server 2015</p></td>
<td><p>False</p></td>
<td><p>Interface utilisateur Lync</p></td>
<td><p>Utilisateur invité à basculer sur l’interface utilisateur de Lync</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 ou Lync Server 2013 (avec les correctifs appropriés)</p></td>
<td><p>True</p></td>
<td><p>Utilisateur invité à basculer sur Skype entreprise</p></td>
<td><p>Skype Entreprise</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 ou Lync Server 2013 (avec les correctifs appropriés)</p></td>
<td><p>False</p></td>
<td><p>Interface utilisateur Lync</p></td>
<td><p>Utilisateur invité à basculer sur l’interface utilisateur de Lync</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 ou Lync Server 2013 (sans correctifs)</p></td>
<td><p>Par défaut</p></td>
<td><p>Mode Lync (possibilité de basculer vers Skype entreprise)</p></td>
<td><p>Interface utilisateur Lync (impossible de basculer vers Skype entreprise)</p></td>
</tr>
</tbody>
</table>


Les versions de correctif requises pour gérer la configuration du client Skype entreprise sont les suivantes:

  - Mise à jour cumulative de Lync Server 2010-février 2015 (4.0.7577.710) pour Lync Server 2010. Pour plus d’informations, voir [mises à jour pour Lync Server 2010](http://go.microsoft.com/fwlink/p/?linkid=532771)

  - Mise à jour cumulative de Lync Server 2013-décembre 2014 (5.0.8308.857) pour Lync Server 2013. Pour plus d’informations, consultez [mises à jour pour Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532772).

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Créer un objet de stratégie de groupe pour modifier le Registre sur un ordinateur joint au domaine

La mise à jour du registre pour afficher l'expérience client Lync la première fois qu'un utilisateur lance le client Skype Entreprise ne doit être effectuée qu'une seule fois. Si vous utilisez un objet de stratégie de groupe pour mettre à jour le registre, vous devez définir l'objet pour créer une valeur et non mettre à jour les données d'une valeur. Lorsque l'objet de stratégie de groupe est appliqué, si la nouvelle valeur n'existe pas, l'objet stratégie de groupe la crée et définit les données de valeur sur 0.

La procédure ci-dessous décrit comment modifier le registre afin que l'expérience client Lync s'affiche la première fois qu'un utilisateur lance le client Skype Entreprise. Vous pouvez également utiliser cette procédure pour mettre à jour le registre afin de désactiver l'écran d'accueil du didacticiel, comme indiqué précédemment.

**Pour créer l’objet GPO**

1.  Démarrez la **Console de gestion des stratégies de groupe**.
    
    Pour plus d'informations sur l'utilisation de la Console de gestion des stratégies de groupe, reportez-vous à l'article [Console de gestion des stratégies de groupe](http://go.microsoft.com/fwlink/?linkid=532759).

2.  Cliquez avec le bouton droit sur le nœud **Objets de stratégie de groupe** et sélectionnez **Nouveau** dans le menu.

3.  Dans la boîte de dialogue **Nouvel objet GPO**, entrez un nom pour l’objet GPO, par exemple, **MakeLyncDefaultUI**, puis cliquez sur **OK**.

4.  Effectuez un clic droit sur le nouvel objet GPO que vous venez de créer, puis sélectionnez **Modifier** dans menu.

5.  Dans **Éditeur de gestion des stratégies de groupe**, développez **Configuration utilisateur**, **Préférences**, **Paramètres Windows**, puis sélectionnez le nœud **Registre**.

6.  Cliquez avec le bouton droit sur le nœud **Registre** , puis sélectionnez **nouvel** \> **élément Registre**.

7.  Dans la boîte de dialogue **Nouvelles propriétés de Registre**, mettez à jour ce qui suit :
    
    
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
    <td><p><strong>Créer</strong></p></td>
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
    <td><p><strong>Type de la valeur</strong></p></td>
    <td><p>REG_BINARY</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Données de la valeur</strong></p></td>
    <td><p>00000000</p></td>
    </tr>
    </tbody>
    </table>


8.  Cliquez sur **OK** pour enregistrer les modifications, puis fermez l'objet GPO.

Ensuite, vous devez lier l'objet GPO créé au groupe d'utilisateurs auquel vous voulez affecter la stratégie, par exemple, une unité d'organisation.

**Pour utiliser l’objet GPO pour affecter la stratégie**

1.  Dans la console de gestion des stratégies de groupe, cliquez avec le bouton droit sur l'unité d'organisation à laquelle vous voulez affecter la stratégie, puis sélectionnez **Lier un objet de stratégie de groupe existant**.

2.  Dans la boîte de dialogue **Sélectionner un objet GPO**, sélectionnez l'objet GPO créé, puis sélectionnez **OK**.

3.  Sur l'ordinateur de l'utilisateur cible, ouvrez une invite de commandes et tapez la commande suivante :
    
    **gpupdate /target:user**
    
    Le message « mise à jour la stratégie… » s'affiche pendant l'application de l'objet GPO. Au terme de l'opération, le message « La mise à jour de la stratégie utilisateur s'est terminée sans erreur. » s'affiche.

4.  Dans l'invite de commandes, tapez la commande suivante :
    
    **gpresult /r**
    
    « Objets de stratégie de groupé affectés » doit s'afficher avec le nom de l'objet GPO créé en-dessous.

Vous pouvez également vérifier que l'objet de stratégie de groupe a mis à jour le registre sur l'ordinateur de l'utilisateur en examinant le registre. Ouvrez l’éditeur du Registre et accédez à la clé de ** \[\_logiciel\\\\de\\l'\] utilisateur\_\\actuel HKEY Microsoft Office Lync** . Si l'objet GPO a mis à jour correctement le registre, la valeur nommée EnableSkypeUI s'affiche avec la valeur 0.

</div>

</div>

<span> </span>

</div>

</div>

</div>

