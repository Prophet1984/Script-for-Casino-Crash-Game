# Script-for-Casino-Crash-Game
An automated script for playing the Crash Game in advanced mode on BC.Game

On BC.Game select > Casino > BC Originals > Crash
In the Crash Game go to Advanced and click on "Add a script", at "Script name" write whatever you like at "Script content" just paste the script.
If you play with a $100 maximum bankroll the "Starting Bet" should not be greater than $0.005 no matter the cryptocurency that you play with, this way you can manage to win around $600 - $800 a month
Have fun!!!

# How to install

Create an account at https://bc.game/i-19sv69gh-n/

- On BC.Game select > Casino > BC Originals > Crash

- In the Crash Game go to Advanced and click on "Add a script", at "Script name" write whatever you like at "Script content" just paste the script below.



var config = {
  scriptTitle: {label: 'Script made by al3xcjc!', type: 'title'},
  baseBet: {label: 'Starting Bet:', value: currency.minAmount, type: 'number'},
  maxBet: {label: 'Maximum Bet:', value: 10000, type: 'number'},
  minBet: {label: 'Minimum Bet:', value: 0, type: 'number'},
  stopBet: {label: 'Stop if Bet is Greater Than:', value: 1e8, type: 'number'},
  basePayout: {label: 'Starting Payout:', value: 2.1, type: 'number'},
  maxPayout: {label: 'Maximum Payout:', value: 10, type: 'number'},
  minPayout: {label: 'Minimum Payout:', value: 2, type: 'number'},
  stopPayout: {label: 'Stop if Payout is Greater Than:', value: 1e8, type: 'number'},
  winRepeat: {label: 'Reset After Win Streak of:', value: 2, type: 'number'},
 
  onBetLossTitle: {label: 'Loss Bet Settings', type: 'title'},
    onBetLoss: {label: '', value: '3', type: 'radio',
      options: [
        {value: '0', label: 'Return to Starting Bet'},
        {value: '1', label: 'Add to Bet'},
        {value: '2', label: 'Subtract From Bet'},
        {value: '3', label: 'Multiply Bet By'},
        {value: '4', label: 'Divide Bet By'}
      ]
    },
  addBetLoss: { label: 'Increase Bet By:', value: 0, type: 'number' },
  subBetLoss: { label: 'Decrease Bet By:', value: 0, type: 'number' },
  mulBetLoss: { label: 'Multiply Bet By:', value: 2, type: 'number' },
  divBetLoss: { label: 'Divide Bet By:', value: 1, type: 'number' },
 
  onPayoutLossTitle :{label: 'Loss Payout Settings', type: 'title'},
    onPayoutLoss: {label: '', value: '0', type: 'radio',
      options: [
        {value: '0', label: 'Return to Starting Payout'},
        {value: '1', label: 'Add to Payout'},
        {value: '2', label: 'Subtract From Payout'},
        {value: '3', label: 'Multiply Payout By'},
        {value: '4', label: 'Divide Payout By'}
      ]
    },
  addPayoutLoss: { label: 'Increase Payout By:', value: 0, type: 'number' },
  subPayoutLoss: { label: 'Decrease Payout By:', value: 0, type: 'number' },
  mulPayoutLoss: { label: 'Multiply Payout By:', value: 1, type: 'number' },
  divPayoutLoss: { label: 'Divide Payout By:', value: 1, type: 'number' },
 
  onBetWinTitle: {label: 'Win Bet Settings', type: 'title'},
    onBetWin: {label: '', value: '0', type: 'radio',
      options: [
        {value: '0', label: 'Return to Starting Bet'},
        {value: '1', label: 'Add to Bet'},
        {value: '2', label: 'Subtract From Bet'},
        {value: '3', label: 'Multiply Bet By'},
        {value: '4', label: 'Divide Bet By'}
      ]
    },
  addBetWin: { label: 'Increase Bet By:', value: 0, type: 'number' },
  subBetWin: { label: 'Decrease Bet By:', value: 0, type: 'number' },
  mulBetWin: { label: 'Multiply Bet By:', value: 1, type: 'number' },
  divBetWin: { label: 'Divide Bet By:', value: 1, type: 'number' },
 
  onPayoutWinTitle :{label: 'Win Payout Settings', type: 'title'},
    onPayoutWin: {label: '', value: '3', type: 'radio',
      options: [
        {value: '0', label: 'Return to Starting Payout'},
        {value: '1', label: 'Add to Payout'},
        {value: '2', label: 'Subtract From Payout'},
        {value: '3', label: 'Multiply Payout By'},
        {value: '4', label: 'Divide Payout By'}
      ]
    },
  addPayoutWin: { label: 'Increase Payout By:', value: 0, type: 'number' },
  subPayoutWin: { label: 'Decrease Payout By:', value: 0, type: 'number' },
  mulPayoutWin: { label: 'Multiply Payout By:', value: 2, type: 'number' },
  divPayoutWin: { label: 'Divide Payout By:', value: 1, type: 'number' },
 
}
 
function main (){
  var baseBet = config.baseBet.value;
  var maxBet = config.maxBet.value;
  var minBet = config.maxBet.value;
  var basePayout = config.minPayout.value;
  var maxPayout = config.maxPayout.value;
  var minPayout = config.minPayout.value;
  var currentBet = config.baseBet.value;
  var currentPayout = config.basePayout.value;
  var onBetWin = config.onBetWin.value;
  var addBetWin = config.addBetWin.value;
  var subBetWin = config.subBetWin.value;
  var mulBetWin = config.mulBetWin.value;
  var divBetWin = config.divBetWin.value;
  var onPayoutWin = config.onPayoutWin.value;
  var addPayoutWin = config.addPayoutWin.value;
  var subPayoutWin = config.subPayoutWin.value;
  var mulPayoutWin = config.mulPayoutWin.value;
  var divPayoutWin = config.divPayoutWin.value;
  var onBetLoss = config.onBetLoss.value;
  var addBetLoss = config.addBetLoss.value;
  var subBetLoss = config.subBetLoss.value;
  var mulBetLoss = config.mulBetLoss.value;
  var divBetLoss = config.divBetLoss.value;
  var onPayoutLoss = config.onPayoutLoss.value;
  var addPayoutLoss = config.addPayoutLoss.value;
  var subPayoutLoss = config.subPayoutLoss.value;
  var mulPayoutLoss = config.mulPayoutLoss.value;
  var divPayoutLoss = config.divPayoutLoss.value;
  var stopPayout = config.stopPayout.value;
  var stopBet = config.stopBet.value;
  var winRepeatCount = config.winRepeat.value
  var winRepeatSet = 1
  var winRepProvision = 0
  var gameStatus = 1
  var gameCounter = 1
 
  game.onBet = function () {
    log.success('Placing Bet For: ' + currentBet + ', At Payout: '+ currentPayout)
   
    game.bet(currentBet, currentPayout).then(function (payout)
        {if (payout > 1)
            {if(!gameStatus)
                {counterReset(true)}
                    log.success('Winner, Winner, Chicken Dinner!')
                        gameStarter(onBetWinSwitch(onBetWin),onPayoutWinSwitch(onPayoutWin))
            }
        else
            {if(gameStatus)
                {gameStatus--}
                    winRepCountReset(true)
                        log.error('We lost that one.')
                            gameStarter(onBetLossSwitch(onBetLoss),onPayoutLossSwitch(onPayoutLoss))
                                gameCounter++
            }
        })
 
function gameStarter(calculatedBet, calculatedPayout)
    {if (currentBet > stopBet)
        {log.error('The bot was stopped because the max bet was reached!');
            game.stop();}
    else
    if (currentPayout > stopPayout)
        {log.error('The bot was stopped because the max payout was reached!');
            game.stop();}
                currentBet = calculatedBet
                currentPayout = calculatedPayout
    }
 
function onBetWinSwitch (switchValue)
{switch(switchValue)
    {case '0':
        return baseBet
      break;
    case '1':
        if(!gameStatus)
            {if(!winRepeatCount)
                {gameStatus++
                    winRepCountReset(true)  
                        return baseBet
                }
            else
                {winRepeatCount--
                    winRepProvision++
                        winRepeatSet--
                        {if (currentBet + (addBetWin) > maxBet)
                            {return maxBet,
                            log.error('Maximum bet reached!')}
                        else
                            return currentBet + (addBetWin)
                        }
                }
            }
        else
            {return baseBet}
                break;
    case '2':
        if(!gameStatus)
            {if(!winRepeatCount)
                {gameStatus++
                    winRepCountReset(true)  
                        return baseBet}
            else
                {winRepeatCount--
                    winRepProvision++
                        winRepeatSet--
                            {if (currentBet - (subBetWin) < minBet)
                                {return minBet,
                                log.error('Minimum bet reached!')}
                            else                        
                                return currentBet - (subBetWin)
                            }
                }
            }
        else
            {return baseBet}
                break;
    case '3':
        if(!gameStatus)
            {if(!winRepeatCount)
                {gameStatus++
                    winRepCountReset(true)  
                        return baseBet}
            else
                {winRepeatCount--
                    winRepProvision++
                        winRepeatSet--
                            {if (currentBet * (mulBetWin) > maxBet)
                                {return maxBet,
                                log.error('Maximum bet reached!')}
                            else                        
                                return currentBet * (mulBetWin)
                            }
                }
            }
    else
    {return baseBet}
        break;
 
        case '4':
        if(!gameStatus)
            {if(!winRepeatCount)
                {gameStatus++
                winRepCountReset(true)  
                    return baseBet}
            else
                {winRepeatCount--
                winRepProvision++
                winRepeatSet--
                    {if (currentBet / (divBetWin) < minBet)
                        {return minBet,
                        log.error('Minimum bet reached!')}
                    else
                        return currentBet / (divBetWin)
                    }
                }
            }
    else
        {return baseBet}
            break;
                           
                   
                   
    }
}
               
function onPayoutWinSwitch (switchValue)
    {switch(switchValue)
        {case '0':
            return basePayout
                break;
        case '1':
            if(!gameStatus)
                {if(!winRepeatCount)
                    {gameStatus++
                        winRepCountReset(true)  
                            return basePayout
                    }
                else
                    {winRepeatCount--
                    winRepProvision++
                    winRepeatSet--
                        {if (currentPayout + (addPayoutWin) > maxPayout)
                            {return maxPayout,
                            log.error('Maximum payout reached!')}
                        else
                            return currentPayout + (addPayoutWin)
                        }
                    }
                }
        else
            {return basePayout}
                break;
        case '2':
            if(!gameStatus)
                {if(!winRepeatCount)
                    {gameStatus++
                    winRepCountReset(true)  
                        return basePayout}
                else
                    {winRepeatCount--
                    winRepProvision++
                    winRepeatSet--
                        {if (currentPayout - (subPayoutWin) < minPayout)
                            {return minPayout,
                            log.error('Minimum payout reached!')}
                        else
                            return currentPayout - (subPayoutWin)
                        }
                    }
                }
            else
                {return basePayout}
                    break;
        case '3':
            if(!gameStatus)
                {if(!winRepeatCount)
                    {gameStatus++
                    winRepCountReset(true)  
                        return basePayout}
                else
                    {winRepeatCount--
                    winRepProvision++
                    winRepeatSet--
                        {if (currentPayout * (mulPayoutWin) > maxPayout)
                            {return maxPayout,
                            log.error('Maximum payout reached!')}
                        else    
                            return currentPayout * (mulPayoutWin)
                        }
                    }
                }
        case '4':
            if(!gameStatus)
                {if(!winRepeatCount)
                    {gameStatus++
                    winRepCountReset(true)  
                        return basePayout}
                else
                    {winRepeatCount--
                    winRepProvision++
                    winRepeatSet--
                        {if (currentPayout / (divPayoutWin) < minPayout)
                            {return minPayout,
                            log.error('Minimum payout reached!')}
                        else  
                            return currentPayout / (divPayoutWin)
                        }
                    }
                }
        else
            {return basePayout}
                break;
    }
}}
function onBetLossSwitch (switchValue)
    {switch(switchValue)
        {case '0':
            return baseBet
                break;
        case '1':
            {if (currentBet + (addBetLoss) > maxBet)
                {return maxBet,
                log.error('Maximum bet reached!')}
            else
                return currentBet + (addBetLoss)}
                break;
        case '2':
            {if (currentBet - (subBetLoss) < minBet)
                {return minBet,
                log.error('Minimum bet reached!')}
            else
                return currentBet - (subBetLoss)}
                break;
        case '3':
            {if (currentBet * (mulBetLoss) > maxBet)
                {return maxBet,
                log.error('Maximum bet reached!')}
            else
                return currentBet * (mulBetLoss)}
                break;
        case '4':
            {if (currentBet / (divBetLoss) < minBet)
                {return minBet,
                log.error('Minimum bet reached!')}
            else
                return currentBet / (divBetLoss)}
                break;
        }  
    }
function onPayoutLossSwitch (switchValue)
    {switch(switchValue)
        {case '0':
            return basePayout
                break;
        case '1':
            {if (currentPayout + (addPayoutLoss) > maxPayout)
                {return maxPayout,
                log.error('Maximum payout reached!')}
            else
                return currentPayout + (addPayoutLoss)}
                break;
        case '2':
            {if (currentPayout - (subPayoutLoss) < minPayout)
                {return minPayout,
                log.error('Minimum payout reached!')}
            else
                return currentPayout - (subPayoutLoss)}
                break;
        case '3':
            {if (currentPayout * (mulPayoutLoss) > maxPayout)
                {return maxPayout,
                log.error('Maximum payout reached!')}
            else
            return currentPayout * (mulPayoutLoss)}
                break;
        case '4':
            {if (currentPayout / (divPayoutLoss) < minPayout)
                {return minPayout ,
                log.error('Minimum payout reached!')}
            else
            return currentPayout / (divPayoutLoss)}
                break;
        }
    }
function counterReset(itsZero)
    {if(itsZero)
        {gameCounter--
        if(!gameCounter)
            {gameCounter++
            return}
                counterReset(true)
        }
    }
function winRepCountReset(itsZero)
    {if(!winRepProvision)
        {return}
            if(itsZero)
            {winRepeatCount++
                winRepProvision--
                    if(!winRepProvision)
                        {return}
                            winRepCountReset(true)
            }
    }
}





- If you play with a $100 maximum bankroll the "Starting Bet" should not be greater than $0.005 this way you can manage to win around $600 - $800 a month
Have fun!!!

# Be careful this is gambeling!!!
Please be responsable and don't become a gambeling adict!
