---
title: "Conf. de la mess. un. MES 2013 pour mess. voc. Microsoft LS 2013"
TOCtitle: "Conf. de la mess. un. MES 2013 pour mess. voc. Microsoft LS 2013"
ms:assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ687983(v=OCS.15)
ms:contentKeyID: 49891253
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la messagerie unifiée Microsoft Exchange Server 2013 pour la messagerie vocale Microsoft Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-04_

Microsoft Lync Server 2013 vous permet de stocker des messages vocaux dans Microsoft Exchange Server 2013, qui apparaîtront ensuite sous forme de messages électroniques dans la boîte de réception des utilisateurs. Cette fonctionnalité était également présente dans les éditions 2010 de Lync Server et d’Exchange, mais la configuration de cette « messagerie unifiée » a été simplifiée dans les éditions 2013 grâce à l’introduction du composant de routeur d’appels de la messagerie unifiée (UM Call Router). Ce composant est installé sur le serveur d’accès au client Exchange 2013 et tous les appels dirigés vers la messagerie unifiée d’Exchange (la messagerie vocale par exemple) sont d’abord routés via le composant de routeur d’appels, puis réacheminés vers le serveur de boîte aux lettres approprié.

Si vous avez déjà configuré l’authentification de serveur à serveur entre Lync Server 2013 et Exchange 2013, vous êtes prêt à installer la messagerie unifiée. Pour ce faire, vous devez d’abord créer et attribuer un nouveau plan de numérotation de messagerie unifiée sur votre serveur Exchange. Par exemple, ces deux commandes (exécutées dans Exchange Management Shell) permettent de configurer un nouveau plan de numérotation à 3 chiffres pour Exchange :

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

Dans la première commande de cet exemple, le paramètre VoIPSecurity et la valeur « Secured » du paramètre indiquent que le canal de signalisation est chiffré à l’aide du protocole TLS (Transport Layer Security). La valeur « SipName » de URIType indique que les messages seront envoyés et reçus à l’aide du protocole SIP et la valeur 1 de CountryOrRegionCode signifie que le plan de numérotation s’applique aux États-Unis.

Dans la seconde commande, la valeur transmise au paramètre ConfiguredInCountryOrRegionGroups indique quels groupes régionaux peuvent être utilisés avec ce plan de numérotation. La valeur de paramètre « Anywhere,\*,\*,\* » définit ce qui suit :

  - Nom du groupe (« Anywhere »)

  - AllowedNumberString (\*, caractère générique indiquant que n’importe quelle chaîne de numéros est autorisée)

  - DialNumberString (\*, caractère générique indiquant que n’importe quel numéro composé est autorisé)

  - TextComment (\*, caractère générique indiquant que n’importe quelle commande de texte est autorisée)

Après avoir créé et configuré le nouveau plan de numérotation, vous devez l’ajouter à votre serveur de messagerie unifiée, puis modifier le mode de démarrage du serveur. Vous devez en particulier définir le mode de démarrage sur Double. Vous pouvez réaliser ces deux tâches dans Exchange Management Shell :

    Set-UmServer -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

Une fois le serveur de messagerie unifiée configuré, vous devez exécuter l’applet de commande Enable-ExchangeCertificate pour vous assurer que votre certificat Exchange est appliqué au service de messagerie unifiée :

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

Une fois le certificat correctement affecté, vous devez arrêter et redémarrer le service MsExchangeUM sur le serveur de messagerie unifiée. Ce service doit être arrêté et redémarré à chaque fois que vous modifiez le mode de démarrage.

Une fois la configuration du serveur de messagerie unifiée terminée, vous pouvez passer à la configuration du routeur d’appels de la messagerie unifiée :

    Set-CsUMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

Comme le mode de démarrage a été modifié, vous devez arrêter et redémarrer le service MsExchangeUMCR sur l’ordinateur qui héberge le routeur d’appels de la messagerie unifiée.

Pour terminer la configuration de la messagerie unifiée, vous devez ensuite créer une stratégie de boîte aux lettres de la messagerie unifiée et utiliser cette stratégie afin d’activer les utilisateurs pour la messagerie unifiée. Vous pouvez créer une stratégie de boîte aux lettres à l’aide d’une commande similaire à celle-ci :

    New-UMMailboxPolicy -ID "RedmondMailboxPolicy" -AllowedCountryOrRegionGroups "Anywhere"

Et vous pouvez activer un utilisateur pour la messagerie unifiée en utilisant une commande semblable à celle-ci :

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

Dans la commande précédente, le paramètre Extensions représente le numéro de poste de l’utilisateur. Dans cet exemple, le numéro de poste de l’utilisateur est le 100.

Une fois sa boîte aux lettres activée, l’utilisateur kenmyer@litwareinc.com doit être en mesure d’utiliser la messagerie unifiée Exchange. Pour vérifier que l’utilisateur peut se connecter à la messagerie unifiée d’Exchange, exécutez l’applet de commande [Test-CsExUMConnectivity](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsExUMConnectivity) dans Lync Server Management Shell:

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Si un second utilisateur a été activé pour la messagerie unifiée, vous pouvez utiliser l’applet de commande [Test-CsExUMVoiceMail](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsExUMVoiceMail) pour vous assurer qu’il est en mesure de laisser un message vocal au premier utilisateur.

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

