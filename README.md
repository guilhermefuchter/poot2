# poot2


enum Level {
    WARNING,
    DEBUG,
    ERROR
}


interface Logger {
    void log(Level level, String message);
}


class LoggerConsole implements Logger {
    @Override
    public void log(Level level, String message) {
       
    }
}


class LoggerFile implements Logger {
    @Override
    public void log(Level level, String message) {
      
    }
}


class LoggerFactory {
    public static Logger getLogger(String type) {
        if (type.equalsIgnoreCase("Console")) {
            return new LoggerConsole();
        } else if (type.equalsIgnoreCase("File")) {
            return new LoggerFile();
        } else {
            throw new IllegalArgumentException("Tipo de logger inválido.");
        }
    }
}


public class Main {
    public static void main(String[] args) {
        // Obtendo instâncias de logger
        Logger consoleLogger = LoggerFactory.getLogger("Console");
        Logger fileLogger = LoggerFactory.getLogger("File");

        // Usando os loggers
        consoleLogger.log(Level.DEBUG, "Mensagem de debug");
        fileLogger.log(Level.ERROR, "Mensagem de erro");
    }
}
