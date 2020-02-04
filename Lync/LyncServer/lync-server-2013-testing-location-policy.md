---
title: 'Lync Server 2013 : test de la stratégie d’emplacement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing location policy
ms:assetid: 23d06fd3-31ee-4480-ba1e-d179a55b8b14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690127(v=OCS.15)
ms:contentKeyID: 63969591
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a954405cb8dbba842250e0545ac8661d4f3795c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-location-policy-in-lync-server-2013"></a>Test de la stratégie d’emplacement dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Échéancier de vérification</p></td>
<td><p>Jour</p></td>
</tr>
<tr class="even">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorisations requises</p></td>
<td><p>Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsLocationPolicy. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de contrôle test-CsLocationPolicy vérifie qu’une stratégie d’emplacement est attribuée à un utilisateur. La stratégie d’emplacement est utilisée pour appliquer les paramètres liés à la fonctionnalité E9-1-1 et à l’emplacement du client. La stratégie d’emplacement détermine si un utilisateur est activé pour E9-1-1 et, si la réponse est « oui », quel est le comportement d’un appel d’urgence. Par exemple, vous pouvez utiliser la stratégie d’emplacement pour définir le numéro qui compose un appel d’urgence (911 aux États-Unis), si la sécurité d’entreprise doit être automatiquement notifiée et comment l’appel doit être routé.

Vous pouvez tester des stratégies d’emplacement sur des utilisateurs ou des sous-réseaux réseau. Si vous exécutez le test sur un sous-réseau (en spécifiant une valeur pour le paramètre de sous-réseau), l’applet de contrôle tente de résoudre la stratégie d’emplacement du sous-réseau. Si aucune stratégie d’emplacement n’est affectée au sous-réseau, la stratégie d’emplacement de l’utilisateur configuré sera récupérée. Si la stratégie de sous-réseau est récupérée correctement, la sortie inclura une valeur LocationPolicyTagID qui commence par le sous-réseau-TagId. Si une stratégie d’emplacement pour le sous-réseau est introuvable, le LocationPolicyTagID commence par user-TagId.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Vous pouvez exécuter l’applet de contrôle test-CsLocationPolicy à l’aide d’un compte de test préconfiguré (voir Configuration de comptes de test pour exécuter des tests Lync Server) ou du compte d’un utilisateur qui est activé pour Lync Server. Pour effectuer cette vérification à l’aide d’un compte de test, vous devez simplement spécifier le nom de domaine complet (FQDN) du pool de serveurs Lync testé. Par exemple :

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

Pour effectuer cette vérification à l’aide d’un compte d’utilisateur réel, vous devez d’abord créer un objet d’informations d’identification Windows PowerShell contenant le nom et le mot de passe du compte. Vous devez alors inclure cet objet Credential et l’adresse SIP attribuée au compte lorsque vous appelez le test-CsLocationPolicy :

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si l’utilisateur spécifié dispose d’une stratégie d’emplacement valide, vous recevrez une sortie semblable à ce qui suit, avec la propriété Result marquée comme **réussie :**

EnhancedEmergencyServicesEnabled : true

LocationPolicyTagID : User-TagId

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : réussite

Latence : 00:00:06.8630376

Error

Diagnostic

Si une stratégie d’emplacement valide est introuvable pour l’utilisateur spécifié, le résultat sera affiché en tant qu’échec et des informations supplémentaires seront enregistrées dans les propriétés d’erreur et de diagnostic :

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:00

Erreur : 404, introuvable

Diagnostic : codeerreur = 4005, source = ATL-CS-001.litwareinc.com,

Raison = URI de destination non activé pour le SIP ou non

Il.

Microsoft. RTC. signalisation. DiagnosticHeader

La sortie précédente indique que le test a échoué, car l’utilisateur spécifié n’est pas valide : le compte n’existe pas, ou l’utilisateur n’a pas été activé pour Lync Server. Vous pouvez vérifier la validité d’un compte et déterminer s’il a été activé pour nm-OCS-14-3e, en exécutant une commande semblable à ce qui suit :

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

Si test-CsLocationPolicy échoue, il est possible que vous souhaitiez réexécuter le test, cette fois-ci, y compris le paramètre Verbose :

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Lorsque le paramètre Verbose est inclus, test-CsLocationPolicy renvoie un compte détaillé de chaque action effectuée lors de la vérification de la stratégie d’emplacement. Par exemple, cette sortie indique que Lync Server ne peut pas se connecter à l’utilisateur de test, probablement en raison d’un mot de passe non valide :

Envoi de la demande d’inscription :

Nom de domaine complet cible = atl-cs-011.litwareinc.com

Adresse SIP de l’utilisateur = sip :kenmyer@litwareinc.com

Port du Bureau d’enregistrement = 5061

Le type d’authentification « IWA » est sélectionné.

Accès à l’enregistrement par SIP/ATL-CS-001. litwareinc. com

Activité « Register » achevée en « 0,0601795 » secondes.

Une exception’la connexion a été refusée. Vérifiez que les informations d’identification correctes sont utilisées et que le compte est actif. ' s’est produite lors du flux de travail.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles les tests-CsLocationPolicy peuvent échouer :

  - Vous avez spécifié un compte d’utilisateur qui n’est pas valide. Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à ce qui suit :
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Le compte d’utilisateur est valide, mais le compte n’est pas activé pour Lync Server. Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à ce qui suit :
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

