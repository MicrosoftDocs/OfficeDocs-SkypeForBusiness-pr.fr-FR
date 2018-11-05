---
title: "Attr. une strat. de mess. voc. hébergée par utilisateur dans Lync Server 2013"
TOCtitle: "Attr. une strat. de mess. voc. hébergée par utilisateur dans Lync Server 2013"
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398919(v=OCS.15)
ms:contentKeyID: 49298958
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Attribuer une stratégie de messagerie vocale hébergée par utilisateur dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2010-11-07_

Le déploiement d’une ou de plusieurs stratégies de messagerie vocale hébergée par utilisateur est facultatif. Si vous déployez des stratégies par utilisateur, vous devez les attribuer explicitement à des utilisateurs, des groupes ou des objets contact.

Pour plus d’informations sur l’attribution ou la désattribution de stratégies de messagerie vocale hébergée par utilisateur, voir les cmdlets suivantes dans la documentation Lync Server Management Shell :

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

## Pour attribuer une stratégie de messagerie vocale hébergée par utilisateur

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez la cmdlet Grant-CsHostedVoicemailPolicy pour attribuer la stratégie de messagerie vocale hébergée par utilisateur à des utilisateurs individuels, des groupes et des objets contact. Par exemple, exécutez :
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    Dans cet exemple, la stratégie de messagerie vocale hébergée ExRedmond est attribuée à l’utilisateur Ken Myer.
    
    **Identité** indique le compte d’utilisateur à modifier. Vous pouvez définir la valeur d’identité dans l’un des formats suivants :
    
      - l’adresse SIP de l’utilisateur ;
    
      - le nom d’utilisateur principal Active Directory ;
    
      - le nom de domaine et le nom d’ouverture de session de l’utilisateur (par exemple, contoso\\kenmyer) ;
    
      - le nom complet des services de domaine Active Directory de l’utilisateur (par exemple, Ken Myer). Vous pouvez recourir à l’astérisque (caractère générique \*) si vous utilisez le nom complet comme identité utilisateur. Par exemple, l’identité « \* Smith » renvoie tous les utilisateurs dont le nom complet se termine par la valeur de chaîne « Smith ».
    
    > [!NOTE]  
    > Le nom de compte SAM Active Directory de l’utilisateur ne peut pas être utilisé comme valeur d’identité, car il n’est pas forcément unique dans la forêt.
