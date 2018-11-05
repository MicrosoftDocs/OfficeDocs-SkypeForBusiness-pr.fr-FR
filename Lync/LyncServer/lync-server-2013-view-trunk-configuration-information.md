---
title: Affichage des informations de configuration de jonction dans Lync Server 2013
TOCTitle: Affichage des informations de configuration de jonction dans Lync Server 2013
ms:assetid: ebe10e14-08c2-4797-9254-9ed89516d5cd
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721927(v=OCS.15)
ms:contentKeyID: 49891594
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Affichage des informations de configuration de jonction dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-22_

Les paramètres de configuration de jonction SIP définissent la relation et les possibilités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un autocommutateur privé IP (PBX) ou le contrôleur de session en périphérie (SBC) du côté fournisseur de services. Ces paramètres spécifient notamment :

  - si la déviation du trafic multimédia doit être activée sur les jonctions ;

  - les conditions dans lesquelles les paquets RTCP sont envoyés ;

  - si le chiffrement SRTP est requis ou non sur chaque jonction.

Lorsque vous installez Microsoft Lync Server 2013, une collection globale de paramètres de configuration de jonction SIP est créée. De plus, les administrateurs peuvent créer des collections de paramètres personnalisées dans l’étendue du site ou du service (uniquement pour le service de passerelle PSTN).

## Affichage des informations de configuration de jonction SIP à l’aide du Panneau de configuration Lync Server

1.  Dans Panneau de configuration Lync Server, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.

2.  Sous l’onglet **Configuration de la jonction** se trouve une liste de toutes vos collections de paramètres de configuration de jonction ; pour chaque collection, les valeurs sont affichées pour les propriétés **Nom**, **Étendue**, **État** et **Déviation du trafic multimédia**, ainsi que le nombre d’**utilisations PSTN**, les **règles de numéro appelant** et les **règles de numéro appelé** associés à la collection. Pour voir des informations supplémentaires sur une collection de paramètres de configuration de jonction, cliquez sur la collection concernée, sur **Modifier**, puis sur **Afficher des détails**. Notez que vous ne pouvez voir les informations détaillées que d’une collection de paramètres de configuration de jonction à la fois.

## Affichage des informations de configuration de jonction SIP à l’aide des cmdlets Lync Server PowerShell

Les paramètres de configuration de jonction SIP peuvent aussi être affichés à l’aide de Lync Server PowerShell et de la cmdlet Get-CsTrunkConfiguration. Celle-ci peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Affichage des informations de configuration de jonction SIP

  - Pour voir les informations concernant tous vos paramètres de configuration de jonction SIP, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur Entrée :
    
        Get-CsTrunkConfiguration
    
    Vous obtiendrez des indications semblables à ceci :
    
        Identity                                  : Global
        OutboundTranslationRulesList              : {}
        SipResponseCodeTranslationRulesList       : {}
        OutboundCallingNumberTranslationRulesList : {}
        PstnUsages                                : {}
        Description                               :
        ConcentratedTopology                      : True
        EnableBypass                              : False
        EnableMobileTrunkSupport                  : False
        EnableReferSupport                        : True
        EnableSessionTimer                        : False
        EnableSignalBoost                         : False
        MaxEarlyDialogs                           : 20
        RemovePlusFromUri                         : False
        RTCPActiveCalls                           : True
        RTCPCallsOnHold                           : True
        SRTPMode                                  : Required
        EnablePIDFLOSupport                       : False
        EnableRTPLatching                         : False
        EnableOnlineVoice                         : False
        ForwardCallHistory                        : False
        Enable3pccRefer                           : False
        ForwardPAI                                : False
        EnableFastFailoverTimer                   : True

Pour plus d’informations, voir la rubrique d’aide pour la cmdlet [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) (contenu éventuellement en anglais).

